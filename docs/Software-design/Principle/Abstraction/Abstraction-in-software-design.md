# Abstraction and architecture

本节对上一节的Abstraction in architecture中所提及内容进行详细论述。

在进行系统设计的时候，[loose coupling](https://en.wikipedia.org/wiki/Loose_coupling) 是架构师的追求目标，为此，架构师们往往进行分解，比如将系统分解为多个 [components](https://en.wikipedia.org/wiki/Software_component#Component_Definition)，然后各[components](https://en.wikipedia.org/wiki/Software_component#Component_Definition)抽象出[**接口**](https://en.wikipedia.org/wiki/Interface_(computing))，它们之间就通过抽象的[**接口**](https://en.wikipedia.org/wiki/Interface_(computing))来进行交互，显然，接口就是对功能的抽象描述。各 [components](https://en.wikipedia.org/wiki/Software_component#Component_Definition) 彼此相互透明（隐藏内部细节），通过[接口](https://en.wikipedia.org/wiki/Interface_(computing))来进行交互。



## 分层

一种常见的分解方式是：分层。这种架构方式普遍存在，在[下一篇](./Abstraction-and-architecture-and-layer.md)进行专门介绍。

## 接口

从上篇开始，我们一直都在接触“接口”这个词语，在上篇中，我把“接口”定义为：对抽象的描述。有必要看看维基百科的[Interface (computing)](https://en.wikipedia.org/wiki/Interface_(computing))，它总结地比较好。

以下两类接口是software engineer经常会使用的两个概念：

- [Application programming interface](https://en.wikipedia.org/wiki/Application_programming_interface) aka API

- [Application binary interface](https://en.wikipedia.org/wiki/Application_binary_interface) aka ABI

在[下一篇](./Abstraction-and-architecture-and-layer.md)的[以层次思想来思考](Abstraction-and-architecture-and-layer.md#以层次思想来思考)节会对两者进行区分。

