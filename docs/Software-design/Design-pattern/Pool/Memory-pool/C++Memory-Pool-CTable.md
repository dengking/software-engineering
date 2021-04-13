# `CTable`

## Source code

```C++
#pragma once

#include <atomic>
#include <new>

/**
 * @brief MALLOC fail，可能原因:
 * 1、OOM
 *
 */
#define ERR_MALLOC			-1
/**
 * @brief table内存空间以及用完
 *
 */
#define ERR_TABLE_FULL		-2

template<class T, uint8_t BLOCK_SIZE_BITS = 16, uint8_t BLOCK_COUNT_BITS = 8>
class CTable
{
	/**
	 * 每块记录数
	 */
	static const uint32_t BLOCK_SIZE = (1 << BLOCK_SIZE_BITS);
	/**
	 * 最多块数
	 */
	static const uint32_t BLOCK_COUNT = (1 << BLOCK_COUNT_BITS);
	/**
	 * 每块内存大小
	 */
	static const size_t BLOCK_MEM_SIZE = BLOCK_SIZE * sizeof(T);

public:
	CTable() :
					m_nBlockCount(0), m_nOffset(0), m_nRecordCount(0)
	{
		assert(BLOCK_SIZE_BITS + BLOCK_COUNT_BITS <= 32);
	}

	~CTable()
	{
		Clear();
	}
	bool Init(int32_t x, int32_t y)
	{
		return true;
	}
	/**
	 * @brief 插入一条记录
	 *
	 * @param lpRecordNo 返回新创建的这条记录的RecordNo
	 * @param lpErrorNo 错误码，是否创建成功
	 * @return 指向新创建的记录
	 */
	T* CreateRecord(uint32_t *lpRecordNo, int32_t *lpErrorNo = nullptr)
	{
		T *lpRecord = nullptr;

		Lock();
		/**
		 * @brief 当当前block可用(有有效内存空间)的时候，会进入到该分支
		 * m_nBlockCount的初始值为0，因此，第一次调用该函数的时候，不会进入该分支，会进入到下一个分支
		 */
		if ((m_nBlockCount > 0) && (m_nOffset < BLOCK_MEM_SIZE))
		{
			lpRecord = (T*) &m_Blocks[m_nBlockCount - 1][m_nOffset];
			m_nOffset += sizeof(T);
			*lpRecordNo = m_nRecordCount++;
		}
		/**
		 * @brief 当需要分配新的block的时候，会进入这个分支，在下面的条件下需要分配新的block
		 * 1、第一次调用该函数
		 * 2、当前block已经满了，需要分配新的block了
		 */
		else if (m_nBlockCount < BLOCK_COUNT)
		{
			/**
			 * 一次性分配BLOCK_MEM_SIZE内存区域，需要注意的是:
			 * new (std::nothrow) T[BLOCK_SIZE] 是一次性分配BLOCK_SIZE条T记录数组
			 * 这个数组的大小为: BLOCK_MEM_SIZE = BLOCK_SIZE * sizeof(T)
			 */
			T *ptr = new (std::nothrow) T[BLOCK_SIZE];
			if (ptr != nullptr)
			{
				m_Blocks[m_nBlockCount++] = (uint8_t*) ptr;
				lpRecord = ptr;
				m_nOffset = sizeof(T);
				*lpRecordNo = m_nRecordCount++;
			}
			else
			{
				if (lpErrorNo != nullptr)
				{
					*lpErrorNo = ERR_MALLOC;
				}
			}
		}
		/**
		 * @brief table已经满了
		 */
		else
		{
			if (lpErrorNo != nullptr)
			{
				*lpErrorNo = ERR_TABLE_FULL;
			}
		}

		Unlock();
		return lpRecord;
	}

	void Clear()
	{
		for (uint32_t i = 0; i < m_nBlockCount; ++i)
		{
			// free(m_Blocks[i]);
			delete[] (T*) m_Blocks[i];
		}
		m_nBlockCount = 0;
		// m_nOffset = BLOCK_MEM_SIZE;
		m_nOffset = (uint32_t) BLOCK_MEM_SIZE;
		m_nRecordCount = 0;
	}
	/**
	 * @brief
	 *
	 * @param nRecordNo
	 * @return
	 */
	T* GetRecord(uint32_t nRecordNo)
	{
		return (T*) (m_Blocks[GetBlock(nRecordNo)] + GetIndex(nRecordNo) * sizeof(T));
	}
	/**
	 * @brief 获得当前的Record数量
	 *
	 * @return
	 */
	uint32_t GetRecordCount() const
	{
		return m_nRecordCount;
	}

private:
	/**
	 * @brief 取block index
	 * @param nRecordNo
	 * @return
	 */
	uint32_t GetBlock(uint32_t nRecordNo)
	{
		return nRecordNo >> BLOCK_SIZE_BITS;
	}

	/**
	 * @brief 取record index
	 * @brief 将nRecordNo的低BLOCK_COUNT_BITS位作为record index
	 * @param nRecordNo
	 * @return
	 */
	uint32_t GetIndex(uint32_t nRecordNo)
	{
		return nRecordNo & (BLOCK_SIZE - 1);
	}

	void Lock()
	{
		/**
		 * 轮训直至m_lock的值为false
		 */
		while (m_lock.test_and_set())
			;
	}

	void Unlock()
	{
		/**
		 * 将m_lock的值置位false
		 */
		m_lock.clear();
	}
private:
	/**
	 * 实现spinning lock
	 */
	std::atomic_flag m_lock = ATOMIC_FLAG_INIT;
	/**
	 * 当前有多少块
	 */
	uint32_t m_nBlockCount;
	/**
	 * 当前块内偏移
	 */
	uint32_t m_nOffset;
	/**
	 * 当前记录数
	 */
	uint32_t m_nRecordCount;
	/**
	 * static array，array的类型是uint8_t *，对应的是byte
	 *  数组的每个元素为指向block的指针
	 */
	uint8_t *m_Blocks[BLOCK_COUNT];
};


```

## Memory space

下面是类比:

|                     | Computer memory                                              | CTable                                                       |
| ------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 最小寻址单位        | byte                                                         | record(类型为`T`)                                            |
| 地址                | memory address                                               | record number                                                |
| hierarchy/structure | computer memory-`contain`->page-`contain`->byte              | `CTable`-`contain`->Block-`contain`->Record                  |
| 地址长度`L`         | TODO: 可以认为是`sizeof(void*)`，即指针类型的长度<br>`PAGE_COUNT_BITS + PAGE_BITS` | `BLOCK_COUNT_BITS + BLOCK_SIZE_BITS`                         |
|                     | `PAGE_COUNT_BITS`                                            | `BLOCK_COUNT_BITS`                                           |
|                     | `PAGE_BITS`                                                  | `BLOCK_SIZE_BITS`                                            |
| 地址长度是否固定    | 固定                                                         | 不固定，最大为32bit                                          |
| 如何寻址            | 1、先定位到page，然后再定位到byte<br>2、从低位到高位，将memory address从第`PAGE_BITS`起到最高位止的数字，作为page index，定位/寻址到指定page<br>3、将memory address的低`PAGE_BITS`为，作为byte index，定位/寻址到byte | 1、先定位到Block，然后再定位到Record<br>2、从低位到高位，将record number从第`BLOCK_SIZE_BITS`起的`BLOCK_COUNT_BITS`位数字，作为block index，定位/寻址到block<br>3、将record number的低`BLOCK_COUNT_BITS`位，作为record index，定位/寻址到record<br> |
| 地址空间大小        | $2^{L}$                                                      | $2^{L} * sizeof(T)$                                          |



### 内存分配单位

|      | Computer memory | CTable |
| ---- | --------------- | ------ |
|      | page            | record |



### 最大memory大小

`BLOCK_COUNT` 个 block；

每个block的大小为: `BLOCK_SIZE * sizeof(T)`

因此，总大小为: `BLOCK_COUNT * BLOCK_SIZE * sizeof(T)`

由于在constructor中，添加了如下限制:

```C++
assert(BLOCK_SIZE_BITS + BLOCK_COUNT_BITS <= 32);
```

即最大为:$2^{32}$条记录。



## Spinning lock

使用 `std::atomic_flag` 实现了一个spinning lock，关于它的实现，参见:

1、工程programming-language的`C++\Language-reference\Basic-concept\Abstract-machine\Memory-model\Memory-model\Atomic-operations-library\std-atomic_flag`章节

2、工程parallel-computing的`Concurrent-computing\Concurrency-control\Mutual-exclusion\Lock\Spinlock`章节；



## Postfix increment operator

上述代码中用到了角度的Postfix increment operator，提醒一点如下: Postfix increment operator先返回原值，然后increment 。

## Linkged page、Unrolled linked list

典型的使用Linkged page、Unrolled linked list来实现memory pool。