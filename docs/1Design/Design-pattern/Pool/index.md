# Pool

在阅读 stackoverflow [What uses are there for “placement new”?](https://stackoverflow.com/questions/222557/what-uses-are-there-for-placement-new) 时，其中提及了memory pool技术，这让我想起了有必要对pool进行总结。

## wikipedia [Pool (computer science)](https://en.wikipedia.org/wiki/Pool_(computer_science))

In [computer science](https://en.wikipedia.org/wiki/Computer_science), a **pool** is a collection of [resources](https://en.wikipedia.org/wiki/System_resource) that are kept[*[clarification needed](https://en.wikipedia.org/wiki/Wikipedia:Please_clarify)*] ready to use, rather than acquired on use and released[*[clarification needed](https://en.wikipedia.org/wiki/Wikipedia:Please_clarify)*] afterwards. In this context, *resources* can refer to 

1) system resources such as [file handles](https://en.wikipedia.org/wiki/File_handle), which are external to a process, or 

2) internal resources such as [objects](https://en.wikipedia.org/wiki/Object_(computing)). 

A pool [client](https://en.wikipedia.org/wiki/Client_(computing)) requests a resource from the pool and performs desired operations on the returned resource. When the client finishes its use of the resource, it is returned to the pool rather than released and lost.[*[clarification needed](https://en.wikipedia.org/wiki/Wikipedia:Please_clarify)*]

The pooling of resources can offer a significant response-time boost in situations that have high cost associated with resource acquiring, high rate of the requests for resources, and a low overall count of simultaneously used resources. Pooling is also useful when the [latency](https://en.wikipedia.org/wiki/Latency_(engineering)) is a concern, because a pool offers predictable times required to obtain resources since they have already been acquired. These benefits are mostly true for system resources that require a [system call](https://en.wikipedia.org/wiki/System_call), or remote resources that require a network communication, such as [database connections](https://en.wikipedia.org/wiki/Database_connection), [socket connections](https://en.wikipedia.org/wiki/Socket_connection), [threads](https://en.wikipedia.org/wiki/Thread_(computing)), and [memory allocation](https://en.wikipedia.org/wiki/Memory_allocation). Pooling is also useful for expensive-to-compute data, notably large graphic objects like [fonts](https://en.wikipedia.org/wiki/Font) or [bitmaps](https://en.wikipedia.org/wiki/Bitmap), acting essentially as a data [cache](https://en.wikipedia.org/wiki/Cache_(computing)) or a [memoization](https://en.wikipedia.org/wiki/Memoization) technique.

> NOTE: optimization、performance

Special cases of pools are [connection pools](https://en.wikipedia.org/wiki/Connection_pool), [thread pools](https://en.wikipedia.org/wiki/Thread_pool), and [memory pools](https://en.wikipedia.org/wiki/Memory_pool).

### Object pools

Main article: [Object pool pattern](https://en.wikipedia.org/wiki/Object_pool_pattern)

Pools can also be used for objects, in which context a *pool* refers to a [design pattern](https://en.wikipedia.org/wiki/Design_pattern) for implementing pools in [object-oriented languages](https://en.wikipedia.org/wiki/Object-oriented_language), such as in the [object pool pattern](https://en.wikipedia.org/wiki/Object_pool_pattern). Objects themselves hold no external resources and only occupy memory, although an already created object avoids the memory allocation required on object creation. Object pools are useful when the cost of [object creation](https://en.wikipedia.org/wiki/Object_creation) is high, but in certain situations this simple object pooling may not be efficient and could in fact decrease performance.[[1\]](https://en.wikipedia.org/wiki/Pool_(computer_science)#cite_note-1)



## Connection pool

参见 `Connection-pool` 章节。

## Memory pool

参见 `Memory-pool` 章节。

## Thread pool

参见工程 `Parallel-computing` 的 `Thread-pool` 章节。

## Process pool

参见 `Prefork-process-pool` 章节。



## Celery pool

stackoverflow [Which pool class should i use prefork, eventlet or gevent in celery?](https://stackoverflow.com/questions/42948547/which-pool-class-should-i-use-prefork-eventlet-or-gevent-in-celery)