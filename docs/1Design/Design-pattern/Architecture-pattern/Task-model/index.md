# Task model



## 关于task model的内容

- [Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)
- [Task parallelism](https://en.wikipedia.org/wiki/Task_parallelism)
- [Task (computing)](https://en.wikipedia.org/wiki/Task_(computing))

## Component

> NOTE: 本节介绍task model的component，即它的组成

### Manager

在task model中，往往有**管理者**（manager）的角色，它负责**控制**整个系统：

1) 调度task，具备**调度者**的角色

关于调度，参见：

- [Scheduling (computing)](https://en.wikipedia.org/wiki/Scheduling_(computing))



2) 监控task，如对task的resource usage进行监控，具备**监控者**的角色

用户可以向manager请求创建task、操作task等。

### Executor

执行task。

### How to model?

> NOTE: 本节介绍如何来进行建模。

使用task model的时候，需要考虑的一些问题：

- task是什么
- **管理者**是什么
- task的**执行者**是什么

下面使用task model来描述一些系统：

1) [Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)

**管理者**是operating system kernel，task是process或thread的执行，它的执行者是CPU。

2) [Celery](https://en.wikipedia.org/wiki/Celery_(software))

Task就是一个一个由用户定义的task function，执行者其实就是process了，**调度者**其实就是它的[task queue](https://en.wikipedia.org/wiki/Celery_(software))了，显然和OS kernel的调度者相比，它的调度策略是非常简单的。

3) Coroutine



## Schedule operations

本节介绍在task model中，对task进行schedule的时候，会执行的一些操作。

### Suspend/yield

yield是主动让渡；

suspend是被动被挂起；

### Resume



### Context switch是task模型的必备操作

本节所描述的context switch是广义的context switch，而不是仅仅局限于process的context switch。因为task model中存在着的并发执行的task，并且管理者会进行调度，所以就会发生context switch，比如：

- git branch，[Frictionless Context Switching](https://git-scm.com/about)

所以，context switch是task模型的必备操作。

与task model相关的另外一个概念就是：task manager，比如[Task Manager (Windows)](https://en.wikipedia.org/wiki/Task_Manager_(Windows))。