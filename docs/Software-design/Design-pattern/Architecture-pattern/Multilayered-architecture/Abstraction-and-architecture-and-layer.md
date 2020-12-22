# 分层

一种常见的架构方式是：分层，具体参见 [abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer)，这是abstraction在architecture领域的一个体现。计算机科学领域的 [abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer) 思想的可谓由来已久且影响深远，在计算机科学的方方面面我们都能够看到它的身影和影响，后面为了描述便利，将[abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer)思想简称为**分层思想**。最能够体现**分层思想**的一个词是：hierarchy（层级），维基百科的[hierarchy](https://en.wikipedia.org/wiki/Hierarchy)对hierarchy的总结是非常详细的，非常值得一读，从中我们可以看到，hierarchy在各个学科中有着广泛的应用：

> Hierarchy is an important concept in a wide variety of fields, such as [philosophy](https://en.wikipedia.org/wiki/Philosophy), [mathematics](https://en.wikipedia.org/wiki/Mathematics), [computer science](https://en.wikipedia.org/wiki/Computer_science), [organizational theory](https://en.wikipedia.org/wiki/Organizational_theory), [systems theory](https://en.wikipedia.org/wiki/Systems_theory), and the [social sciences](https://en.wikipedia.org/wiki/Social_sciences) (especially [political philosophy](https://en.wikipedia.org/wiki/Political_philosophy)).

其实从这上述论断中我们也可以倒推出：分层思想在各个学科中有着广泛的应用，其实如果往更深层次去思考的话，分层思想其实是一种结构化的思维，关于这个还需要进行一些阅读。

下面是我所总结的计算机科学的各个领域中分层的应用：

## Architecture

作为软件工程师，我们常常听到architecture（架构）这个词，并且有一个高端职位叫做architect（架构师）。软件或系统的架构为我们描述的系统的结构、组成部分、各部分之间的接口。分层思想对architecture影响体现在各种各样的**层次化结构**，比如

### Architecture of [computing system](https://en.wikipedia.org/wiki/Computing)

参见：[Architecture-of-computing-system](https://dengking.github.io/Linux-OS/Architecture/Architecture-of-computing-system/)

计算机系统如此复杂，各个层次之间只需要通过抽象的[接口](https://en.wikipedia.org/wiki/Interface_(computing))就可以进行交互，完全无需了解对方具体的细节。请想想，如果不这样的话，则多么复杂。抽象简化了计算机系统，带来了分工，带来了效率。抽象，掩盖细节，提高了易用性。

### Architecture of compiler

参见：[The Structure of a Compiler](https://dengking.github.io/compiler-principle/Chapter-1-Introduction/1.2-The-Structure-of-a-Compiler/)

#### 中间表示(IR)

编译器分为前段和后端，中间表示理解前段与后端。也可以说中间表示是两者之间的接口。



## [Communication protocol](https://en.wikipedia.org/wiki/Communication_protocol)

各种各样的通信协议可以说是最最能够体现分层思想的了，在[Communication protocol](https://en.wikipedia.org/wiki/Communication_protocol)的[Protocol design](https://en.wikipedia.org/wiki/Communication_protocol#Protocol_design)章节中就总结了协议涉及的思想：[Layering](https://en.wikipedia.org/wiki/Communication_protocol#Layering)。除此之外，参加：[Hierarchical internetworking model](https://en.wikipedia.org/wiki/Hierarchical_internetworking_model)。

下面列举了几个常见协议，它们都能非常好地体现了分层思想：

### [OSI model](https://en.wikipedia.org/wiki/OSI_model)

[OSI model](https://en.wikipedia.org/wiki/OSI_model)可以说是分层思想的最佳体现，下面是摘自[OSI model](https://en.wikipedia.org/wiki/OSI_model)：

> The **Open Systems Interconnection model** (**OSI model**) is a [conceptual model](https://en.wikipedia.org/wiki/Conceptual_model) that characterizes and standardizes the communication functions of a [telecommunication](https://en.wikipedia.org/wiki/Telecommunication) or computing system without regard to its underlying internal structure and technology. Its goal is the interoperability of diverse communication systems with standard [communication protocols](https://en.wikipedia.org/wiki/Communication_protocols). The model partitions a communication system into [abstraction layers](https://en.wikipedia.org/wiki/Abstraction_layer). The original version of the model had seven layers.
>
> A layer serves the layer above it and is served by the layer below it. 

上面这段话其实描述了**分层**所带来的好处：interoperability ，各层之间互相透明（隐藏内部结构和技术），通过约定好的[communication protocols](https://en.wikipedia.org/wiki/Communication_protocols)进行交互。

OSI model by [layer](https://en.wikipedia.org/wiki/Abstraction_layer)

|      |   [layer](https://en.wikipedia.org/wiki/Abstraction_layer)   |
| :--: | :----------------------------------------------------------: |
|  7   | [Application layer](https://en.wikipedia.org/wiki/Application_layer) |
|  6   | [Presentation layer](https://en.wikipedia.org/wiki/Presentation_layer) |
|  5   | [Session layer](https://en.wikipedia.org/wiki/Session_layer) |
|  4   | [Transport layer](https://en.wikipedia.org/wiki/Transport_layer) |
|  3   | [Network layer](https://en.wikipedia.org/wiki/Network_layer) |
|  2   | [Data link layer](https://en.wikipedia.org/wiki/Data_link_layer) |
|  1   | [Physical layer](https://en.wikipedia.org/wiki/Physical_layer) |



### [Internet protocol suite](https://en.wikipedia.org/wiki/Internet_protocol_suite)





## [Database abstraction layer](https://en.wikipedia.org/wiki/Database_abstraction_layer)

这段描述非常好：

> A **database abstraction layer** (**DBAL** or **DAL**) is an [application programming interface](https://en.wikipedia.org/wiki/Application_programming_interface) which unifies the communication between a computer application and [databases](https://en.wikipedia.org/wiki/Database) such as [SQL Server](https://en.wikipedia.org/wiki/MSSQL), [DB2](https://en.wikipedia.org/wiki/IBM_DB2), [MySQL](https://en.wikipedia.org/wiki/MySQL), [PostgreSQL](https://en.wikipedia.org/wiki/PostgreSQL), [Oracle](https://en.wikipedia.org/wiki/Oracle_database) or [SQLite](https://en.wikipedia.org/wiki/SQLite). 



## 以层次思想来思考

### 问题出现在哪个层次

在多层次中，当出现问题是，就需要进行这样的考虑。

### 不同层次相互借用概念

当我们站在计算机系统的不同层次来思考，我们会发现不同层次之间会存在着大量的相互概念借用，或者说，不同层次使用不同的术语来表示类似的概念。比如：

#### 案例

不同层次描述本质上非常类似的事务有着不同的说法，比如在[Linux-OS-kernel-is-event-driven](https://dengking.github.io/Linux-OS/Kernel/Book-Understanding-the-Linux-Kernel/Guide/Linux-OS's-interaction-with-the-hardware/Linux-OS-kernel-is-event-driven/)中总结的：

| Hardware                                                     | Software                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Interrupt-driven](https://en.wikipedia.org/wiki/Interrupt)  | [Event-driven architecture](https://en.wikipedia.org/wiki/Event-driven_architecture) / [Event-driven programming](https://en.wikipedia.org/wiki/Event-driven_programming) |
| [Interrupt](https://en.wikipedia.org/wiki/Interrupt)         | [Event (computing)](https://en.wikipedia.org/wiki/Event_(computing)) |
| [Interrupt handler](https://en.wikipedia.org/wiki/Interrupt_handler)/[Interrupt service routine](https://en.wikipedia.org/wiki/Interrupt_handler) | [Event handler](https://en.wikipedia.org/wiki/Event_(computing)#Event_handler)/[Callback function](https://en.wikipedia.org/wiki/Callback_(computer_programming)) |

各种interrupt就是所谓的event。

#### 案例

linux的[epoll](https://en.wikipedia.org/wiki/Epoll)的[triggering mode](https://en.wikipedia.org/wiki/Epoll#Triggering_mode)借用了[Interrupt](https://en.wikipedia.org/wiki/Interrupt)的[triggering methods](https://en.wikipedia.org/wiki/Interrupt#Triggering_methods)概念。

#### 案例

在[Understanding.The.Linux.kernel.3rd.Edition](https://www.oreilly.com/library/view/understanding-the-linux/0596005652/)的Chapter 4. Interrupt定义了Synchronous interrupt的概念，它是Hardware层的概念，在OS层，与它对应的是[Signal](http://en.wikipedia.org/wiki/Signal_(IPC))。



### 不同层次使用不同语言

在上一节《编程语言的发展史》中已经对此进行了分析。

不同层次使用不同的语言：[Very high-level programming language](https://en.wikipedia.org/wiki/Very_high-level_programming_language)、高级编程语言（[High-level programming language](https://en.wikipedia.org/wiki/High-level_programming_language)）、低级编程语言（[Low-level programming language](https://en.wikipedia.org/wiki/Low-level_programming_language)），



#### 不同层次的语言之间的转换

比如compiler就是执行这个目的的。参见龙书[Chapter 7 Run-Time Environments](https://dengking.github.io/compiler-principle/Chapter-7-Run-Time-Environments/)。

#### API VS ABI 

当我们以层次思想来思考ABI和API时，就会发现对于两者的区分是非常容易的：它们是不同的language的[interface](https://en.wikipedia.org/wiki/Interface_(computing))。API是hight-level programming language的程序之间进行交互的[interface](https://en.wikipedia.org/wiki/Interface_(computing))，而ABI则是machine language的程序之间进行交互的[interface](https://en.wikipedia.org/wiki/Interface_(computing))。

需要注意的是，正如在上一节在《编程语言的发展史》中所提及的：

> 不管多么高级的语言最终都需要被翻译（compiler或interpreter）为[machine language](https://en.wikipedia.org/wiki/Machine_code)才能够被机器执行

所以需要定义hight-level programming language中的各种概念如何翻译为machine language，这部分内容也是ABI中所包含的，比如calling convention等。	

[![img](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Linux_API_and_Linux_ABI.svg/300px-Linux_API_and_Linux_ABI.svg.png)](https://en.wikipedia.org/wiki/File:Linux_API_and_Linux_ABI.svg)

> [Linux kernel](https://en.wikipedia.org/wiki/Linux_kernel) and [GNU C Library](https://en.wikipedia.org/wiki/GNU_C_Library) define the [Linux API](https://en.wikipedia.org/wiki/Linux_kernel_interfaces#Kernel–user_space_API). After compilation, the binaries offer an ABI; keeping this ABI stable over a long time is important for [ISVs](https://en.wikipedia.org/wiki/Independent_software_vendor).



## 总结

在计算机科学中，分层，抽象，接口，这词可以看做是同义词。

## 分层带来的价值

分层带来解耦，分层带来简化

### [Separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns)



### [Portability](https://en.wikipedia.org/wiki/Software_portability)

如

- [Diversity of operating systems and portability](https://en.wikipedia.org/wiki/Operating_system#Diversity_of_operating_systems_and_portability)

抽象层带来移植性

### 分层带来安全

在[Kernel (operating system)](https://en.wikipedia.org/wiki/Kernel_(operating_system))中有这样的描述：

> [kernel space](https://en.wikipedia.org/wiki/Kernel_space). [user space](https://en.wikipedia.org/wiki/User_space). 
>
> This separation prevents user data and kernel data from interfering with each other and causing instability and slowness, as well as preventing malfunctioning application programs from crashing the entire operating system.

分层带来隔离，进而带来安全

### 分层带来[modularity](https://en.wikipedia.org/wiki/Modular_programming)

在[Kernel (operating system)](https://en.wikipedia.org/wiki/Kernel_(operating_system))中有这样的描述。



## 分层与栈、pipeline

一般，会将按照分层设计的系统称为栈，比如协议栈，另外一个与此相关的词是pipeline。显然，无论pipeline还是栈，它们都是线性结构，这与分层结构是线性结构是相契合的。

See also:

[Solution stack](https://en.wikipedia.org/wiki/Solution_stack)





## See also:

- [Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))

- [Abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer)

- [Layer (object-oriented design)](https://en.wikipedia.org/wiki/Layer_(object-oriented_design))

  

