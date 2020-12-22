# Abstraction and architecture

在进行系统设计的时候，[loose coupling](https://en.wikipedia.org/wiki/Loose_coupling) 是架构师的追求目标，为此，架构师们往往进行分解，比如将系统分解为多个 [components](https://en.wikipedia.org/wiki/Software_component#Component_Definition)，然后各[components](https://en.wikipedia.org/wiki/Software_component#Component_Definition)抽象出[**接口**](https://en.wikipedia.org/wiki/Interface_(computing))，它们之间就通过抽象的[**接口**](https://en.wikipedia.org/wiki/Interface_(computing))来进行交互，显然，接口就是对功能的抽象描述。各 [components](https://en.wikipedia.org/wiki/Software_component#Component_Definition) 彼此相互透明（隐藏内部细节），通过[接口](https://en.wikipedia.org/wiki/Interface_(computing))来进行交互。



## 分层

一种常见的分解方式是：分层。这种架构方式普遍存在，在`Software-design\Design-pattern\Architecture-pattern\Multilayered-architecture`中进行了专门介绍。

## 接口

在`./Interface`章节中对interface进行了具体的描述。