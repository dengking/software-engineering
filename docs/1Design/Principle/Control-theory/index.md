# Control theory

本章的标题的含义是：控制论。

control是一个非常抽象的、宽泛的概念，我是在学习[Inversion of control](https://en.wikipedia.org/wiki/Inversion_of_control)的时候，开始思考它的。从“control”概念出发，能够帮助我们理解很多computer science中的问题，更加重要的是：建立起这个概念，能够让我们从更加高的角度来思考我们遇到的问题，在“What is control”中，我们将从“relation”的角度来描述“control”，基于“relation”的描述，能够帮助我们分析复杂的系统中各个角色之间的关系、从而做出更好的设计。

## What is control ? 

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



## What is control theory ?

本文标题的control theory是我自己创造的一个名词，我仅仅是为了便于后续在其它的文章中引用它。后来Google后才发现: control theory 其实是一门学科，参见 wikipedia [Control theory](https://en.wikipedia.org/wiki/Control_theory)。我不怎么严谨的认为：本文所讨论的control theory其实也是属于专业领域的control theory的。

### Examples

| example                | explanation                                         |                                                              |
| ---------------------- | --------------------------------------------------- | ------------------------------------------------------------ |
| GC                     | GC **控制着** object的lifetime                      | wikipedia [Garbage collection](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)) |
| Scheduler              | Scheduler **控制着** process的执行                  | wikipedia [Scheduling(computing)](https://en.wikipedia.org/wiki/Scheduling_(computing)) |
| DI container           | Container **控制着** dependency的injection          | wikipedia [Dependency injection](https://en.wikipedia.org/wiki/Dependency_injection) |
| Event-driven framework | Framework **控制着** event和event handler之间的映射 | - wikipedia [Event-driven architecture](https://en.wikipedia.org/wiki/Event-driven_architecture) <br>- wikipedia [Event-driven programming](https://en.wikipedia.org/wiki/Event-driven_programming) |



## Take control to make it computational

在工程discrete的`Relation-structure-computation\Computation\Make-it-computational`章节中讨论了"make it computational"。

对于未知的、无序的、不可靠的，我们不可依赖于，它们都是uncomputational的，为了make it computational，我们要进行显式的、可靠的控制(take control)

1、要么IOC，将控制权交给framework，由它来进行控制;

2、要么由programmer主动take control，加入ordering，从而make it computational;

### Ordering

Take control->主动加入ordering->make it computational。

参见工程discrete的`Relation-structure-computation\Computation\Make-it-computational\Ordering`章节。

## Give control to programmer

"give control to programmer"能够解释computer science中的非常多的内容。

### Programming language给予programmer对computation的控制

Programming language提供的各种specifier、language support library基于了programmer对computation的控制，关于这个观点，参见工程programming-language的`Theory\Programming-language\How-to-master-programming-language`章节。

### Coroutine and cooperative-multitasking

"coroutine"基于了programmer schedule的权利。

OS kernel是IOC，由它来控制process的schedule。

## 改变control relation

在一个system中，我们往往处于各种原因需要改变control relation，改变control relation意味着**控制权**的移交，下面是一些例子: 



### IOC

IOC就是典型的改变control relation的例子：将**控制权**移交给framework。将在下一个章节对它进行介绍。

### Automatic memory management

automatic memory management就是典型的将memory management的control移交。

#### GC

#### `std::shared_ptr`

### Framework

#### Event-driven framework

event driven and call back

## draft

控制权，掌控控制权，IOC其实准确地说

控制论：process的执行收scheduler的控制，即受控于。

reverse of control： dependence injection

主动close network connection，而不是依赖于network library



控制论在computer science中普遍存在，需要搞清楚受控方、主控方，下面是一些例子:
\- IOC
\- GC
\- event driven and call back

有的时候，我们是需要取得控制权的，比如之前的network IO

