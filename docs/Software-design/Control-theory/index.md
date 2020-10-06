# Control theory

本章的标题的含义是：控制论。

control是一个非常抽象的概念，我是在学习[Inversion of control](https://en.wikipedia.org/wiki/Inversion_of_control)的时候，开始思考它的。

## What is control

语言的迷惑性在于: 同一个词语，有的时候表示的是动词，有的时候表示的名词；“control”这个词语就是这样的:

| 词性 | 解意                         | example                                                      |
| ---- | ---------------------------- | ------------------------------------------------------------ |
| 名词 | power to direct or determine | [control flow](https://en.wikipedia.org/wiki/Control_flow)、[inversion of control](https://en.wikipedia.org/wiki/Inversion_of_control) |
| 动词 |                              | control the company                                          |

从relation的角度来看: control（名词）是一种关系:

```
控制方---control----受控方
```



控制方 拥有 着 **控制权**。

“受控于”。

### Examples

| example                | explanation                                         |                                                              |
| ---------------------- | --------------------------------------------------- | ------------------------------------------------------------ |
| GC                     | GC **控制着** object的lifetime                      | wikipedia [Garbage collection](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)) |
| Scheduler              | Scheduler **控制着** process的执行                  | wikipedia [Scheduling(computing)](https://en.wikipedia.org/wiki/Scheduling_(computing)) |
| DI container           | Container **控制着** dependency的injection          | wikipedia [Dependency injection](https://en.wikipedia.org/wiki/Dependency_injection) |
| Event-driven framework | Framework **控制着** event和event handler之间的映射 | - wikipedia [Event-driven architecture](https://en.wikipedia.org/wiki/Event-driven_architecture) <br>- wikipedia [Event-driven programming](https://en.wikipedia.org/wiki/Event-driven_programming) |



控制权，掌控控制权，IOC其实准确地说

控制论：process的执行收scheduler的控制，即受控于。

reverse of control： dependence injection

主动close network connection，而不是依赖于network library

控制论在computer science中普遍存在，需要搞清楚受控方、主控方，下面是一些例子:
\- IOC
\- GC
\- event driven and call back

有的时候，我们是需要取得控制权的，比如之前的network IO



## 改变control relation

在一个system中，我们往往处于各种原因需要改变control relation，下面是一些例子: 

### Dangling pointer

在TCP SDK（网络库，可以认为是一个[Event-driven architecture](https://en.wikipedia.org/wiki/Event-driven_architecture)），一般采 [Publish–subscribe pattern](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern)、[Observer pattern](https://en.wikipedia.org/wiki/Observer_pattern) ；这两种模式的一个共性就是: 将**Listener对象**传入到TCP SDK（网络库），一般是通过pointer、reference的方式进行注册；TCP SDK会network的各种event通过回调**Listener对象**的成员方法通知到应用层，比如将**连接断开**的事件通过调用**Listener对象**的`OnDisconnected`通知到应用层。下面描述了在这种模式下非常容易出现的一个问题:

如果TCP SDK的网络断开是**异步**的，并且不对**Listener对象**的lifetime的进行控制；那么就存在这样的一种可能: **Listener对象**已经被释放了，而TCP SDK并不知晓，依然调用`OnDisconnected`；

则这样就发生了本节标题中描述的dangling pointer错误，导致程序core dump。

对网络连接的断开、object的lifetime不就行控制而导致的问题，修正方法是：首先将网络连接关闭（使用阻塞的方法），带关闭完成后（`OnDisconnected`被调用了），再来析构`Listener`对象。



### IOC

IOC就是典型的改变control relation的例子。将在下一个章节对它进行介绍。