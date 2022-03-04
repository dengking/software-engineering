# Code coverage



## zhihu [什么是代码覆盖率？](https://www.zhihu.com/question/22244568)



## zhihu [实际软件工程中是否真的需要100%代码覆盖率（code coverage）？](https://www.zhihu.com/question/29528349) 

### [Milo Yip的回答](https://www.zhihu.com/question/29528349/answer/44914382) 

> NOTE: 
>
> 1、作者结合自己的项目经验来谈的



### [ThoughtWorks中国](https://www.zhihu.com/question/29528349/answer/236076742)

把测试覆盖作为质量目标没有任何意义，我们应该把它作为一种发现未被测试覆盖的代码的手段。

**所以100%的代码覆盖率还值得追求吗?**

当然，这应该是每个程序员毕生的追求之一，但是如果从项目角度考虑**ROI(投入产出比)**，对于需要快速上线的短期项目，需要注重的是让测试覆盖核心功能代码。如果你的项目是一个长期项目，那么**高覆盖率**是非常有必要的，它意味着**高可维护性**，以及**更少的bug**。(前提是你的测试采用TDD/BDD方式编写，我见过将测试代码写的一团糟的人，看着他的代码，我宁愿重新写一遍)

> NOTE: 
>
> 一、关于TDD/BDD，参见:
>
> [Test-driven development](https://infogalactic.com/info/Test-driven_development)
>
> [Behavior-driven development](https://infogalactic.com/info/Behavior-driven_development)

**那么对于一个项目来说，覆盖率应该达到多少？**

其实没有适用于所有项目的数值，每个项目都应有自己的阈值，但共性是，测试必须覆盖主要业务场景，代码的逻辑分支也必须尽可能的覆盖。

**如何改进你的项目代码覆盖率？**

**首先**我们要阅读和理解项目代码，找出其中需要测试并且与业务强相关的代码，结合sonar等代码质量管理平台，从代码编写规范、复杂度、重复代码等方面进行代码重构，进一步提高项目的可维护性与可读性。

这也意味着重构，重构的同时，你需要更多的测试来保证你重构代码的正确性。

**其次**要对code coverage进行度量分析，那么我们应该怎么度量code coverage？



![img](https://pic2.zhimg.com/50/v2-04dd1f01df4e80503ffe6969d4944518_hd.jpg?source=1940ef5c)![img](https://pic2.zhimg.com/80/v2-04dd1f01df4e80503ffe6969d4944518_720w.jpg?source=1940ef5c)



一般来说我们从以下四个维度来度量，如上图所示:

1. **行覆盖率**（line coverage）：度量被测代码中每个可执行语句是否都被执行到，但不包括java import，空行，注释等。
2. **函数覆盖率**（function coverage）：度量被测代码中每个定义的函数是否都被调用。
3. **分支覆盖率**（branch coverage）：度量被测代码中每一个判定的分支是否都被测试到。
4. **语句覆盖率**（statement coverage）：度量被测代码是否每个语句都被执行。

所以行覆盖率的高低不能说明项目的好坏，我们要从多方面进行思考，一般我们遵循的标准应是：**函数覆盖率 > 分支覆盖率 > 语句覆盖率\****。

**代码覆盖率最重要的意义在于：**

- 阅读分析之前项目中未覆盖部分的代码，进而反推在前期QA以及相关测试人员在进行黑盒测试设计时是否考虑充分，没有覆盖到的代码是否是测试设计的盲点，为什么没有考虑到？是需求或者UX设计不够清晰，还是测试设计的理解有误。
- 检测出程序中的废代码，可以逆向反推代码设计中不合理的地方，提醒设计/开发人员理清代码逻辑关系，提升代码质量。
- 代码覆盖率高不能说明代码质量高，但是反过来看，代码覆盖率低，代码质量绝对不会高到哪里去，可以作为测试自我审视的重要工具之一。

**结束语**

单元测试的覆盖率并不只是为了取悦客户或者管理层的数据，它能够实实在在反应项目中代码的健康程度，帮助我们更好的改善了代码的质量，增加了我们对所编写代码的信心。



## wikipedia [Code coverage](http://en.wikipedia.org/wiki/Code_coverage)



### Coverage criteria

> NOTE: 
>
> 各种覆盖的指标




