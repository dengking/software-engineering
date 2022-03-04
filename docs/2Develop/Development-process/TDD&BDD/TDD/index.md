# Test-driven development



## wikipedia [Test-driven development](https://en.wikipedia.org/wiki/Test-driven_development)

**Test-driven development** (**TDD**) is a [software development process](https://en.wikipedia.org/wiki/Software_development_process) relying on software requirements being converted to [test cases](https://en.wikipedia.org/wiki/Test_case) before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases. This is opposed to software being developed first and test cases created later.



## baike [TDD（测试驱动开发(Test-Driven Development)）# TDD原则](https://baike.baidu.com/item/TDD/9064369?fr=aladdin) 

1、独立测试：

不同代码的测试应该相互独立，一个类对应一个测试类（对于C代码或C++全局函数，则一个文件对应一个测试文件），一个函数对应一个测试函数。

用例也应各自独立，每个用例不能使用其他用例的结果数据，结果也不能依赖于用例执行顺序。 

~~一个角色：开发过程包含多种工作，如：编写测试代码、编写产品代码、代码重构等。做不同的工作时，应专注于当前的角色，不要过多考虑其他方面的细节。~~

> 不理解上面这段话的含义

2、测试列表：

代码的功能点可能很多，并且需求可能是陆续出现的，任何阶段想添加功能时，应把相关功能点加到测试列表中，然后才能继续手头工作，避免疏漏。

3、测试驱动：

即利用测试来驱动开发，是TDD的核心。要实现某个功能，要编写某个类或某个函数，应首先编写测试代码，明确这个类、这个[函数](https://baike.baidu.com/item/函数/18686609)如何使用，如何测试，然后在对其进行设计、编码。

4、先写断言：

编写测试代码时，应该首先编写判断代码功能的断言语句，然后编写必要的辅助语句。

5、可测试性：

产品代码设计、开发时的应尽可能提高可测试性。每个代码单元的功能应该比较单纯，“各家自扫门前雪”，每个类、每个函数应该只做它该做的事，不要弄成大杂烩(**single responsibility principle**)。尤其是增加新功能时，不要为了图一时之便，随便在原有代码中添加功能，对于C++编程，应多考虑使用子类、继承、重载等OO方法(**封装**)。

> NOTE: 
>
> 这段总结地不错

6、及时重构：

对结构不合理，重复等“味道”不好的代码，在测试通过后，应及时进行重构。

7、小步前进：

软件开发是复杂性非常高的工作，小步前进是降低复杂性的好办法。



## 知乎 [TDD 与 BDD 仅仅是语言描述上的区别么？ - 程序人生的回答](https://www.zhihu.com/question/20161970/answer/1341811526) 

这对于**单元测试**与开发是很有用的一种实践。因为TDD是要求在写代码之前就要想好怎么测，测什么，这解决了**可测性**低的问题。另外，TDD还可以提高代码的**测试覆盖率**，令bug在**编码阶段**就能被发现。减少上线后发现问题，修复问题的指数级增长成本。

> NOTE: 
>
> 非常好的解释了为什么使用TDD。