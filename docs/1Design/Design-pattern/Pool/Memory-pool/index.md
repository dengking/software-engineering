# Memory pool



## wikipedia [Memory pool](https://en.wikipedia.org/wiki/Memory_pool)

**Memory pools**, also called [fixed-size blocks allocation](https://en.wanweibaike.com/wiki-Fixed-size_blocks_allocation), is the use of [pools](https://en.wanweibaike.com/wiki-Pool_(computer_science)) for [memory management](https://en.wanweibaike.com/wiki-Memory_management) that allows [dynamic memory allocation](https://en.wanweibaike.com/wiki-Dynamic_memory_allocation) comparable to [malloc](https://en.wanweibaike.com/wiki-Malloc) or [C++](https://en.wanweibaike.com/wiki-C%2B%2B)'s [operator new](https://en.wanweibaike.com/wiki-New_(C%2B%2B)). As those implementations suffer from [fragmentation](https://en.wanweibaike.com/wiki-Fragmentation_(computer)) because of variable block sizes, it is not recommendable to use them in a [real time system](https://en.wanweibaike.com/wiki-Real-time_computing) due to performance. A more efficient solution is preallocating a number of memory blocks with the same size called the **memory pool**. The application can allocate, access, and free blocks represented by [handles](https://en.wanweibaike.com/wiki-Handle_(computing)) at [run time](https://en.wanweibaike.com/wiki-Run_time_(program_lifecycle_phase)).



## Implementation

一、这是一种非常重要的optimization方式，在下面的工程、章节中，使用到了它:

1、rapidXML

2、zeux-pugiXML

3、`Expert-Jeff-Preshing\Library-cpp11-on-multicore`

4、spdlog



### github [cacay/Memory*Pool*](https://github.com/cacay/MemoryPool)





### Boost.Pool

https://www.boost.org/

https://www.boost.org/doc/libs/1_75_0/

[Pool](https://www.boost.org/doc/libs/1_75_0/libs/pool/)

Memory pool management.

theboostcpplibraries [Chapter 4. Boost.Pool](https://theboostcpplibraries.com/boost.pool)



### TODO

thinkingeek [A very simple memory pool in C++11](https://thinkingeek.com/2017/11/19/simple-memory-pool/)

stackoverflow [What are the usual im­ple­men­ta­tion de­tails be­hind mem­ory pools?](https://stackoverflow.com/questions/30508183/what-are-the-usual-im-ple-men-ta-tion-de-tails-be-hind-mem-ory-pools)

