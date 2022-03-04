# TDD && BDD

一、TDD、BDD两者所强调的重点是不同的、两者是相互补充的，并不矛盾，在实际的软件研发过程中，两者是可以同时运用的



## zhihu [TDD 与 BDD 仅仅是语言描述上的区别么？](https://www.zhihu.com/question/20161970)



### [程序人生的回答](https://www.zhihu.com/question/20161970/answer/1341811526)

> NOTE: 
>
> 非常好地介绍了TDD、BDD

#### TDD （Test-Driven Development)

**概括来说，是先写一小段某个功能的测试代码，测试失败，再写实现代码，测试成功，再迭代下一个功能。**

这对于单元测试与开发是很有用的一种实践。因为TDD是要求在写代码之前就要想好怎么测，测什么，这解决了可测性低的问题。另外，TDD还可以提高代码的测试覆盖率，令bug在编码阶段就能被发现。减少上线后发现问题，修复问题的指数级增长成本。

> NOTE: 非常好的解释了为什么需要使用TDD

然而，**TDD也有它的不足：**

1、它解决的是代码级的验证，但是测试代码与需求的符合问题解决得不是很好，非技术人员、客户看不懂代码，无法评审测试是否符合需求。

2、测试代码可能写得太大或者太小，令开发人员效率下降。这与测试代码与功能对应不起来有很大关系。

于是，有一些人扩展了TDD，提出了BBD。

#### BDD（ Behaviour-Driven Development)

他们发现，如果将自然语言按照一些简单语法组织起来，代码将会非常容易解释与处理。使用这种方法可以让非技术人员、客户可以参与到需求的确认与验收当中。

我们看一下两个例子

```text
Scenario: Refunded items should be returned to stock
  Given a customer bought a black sweater from me
    and I have three black sweaters left in stock.
   When he returns the sweater for a refund
   then I should have four black sweaters in stock.


场景： 微信聊天
假如  手机安装了微信
当  用户打开微信
那么  手机会出现用户的微信聊天界面
```

以上就是BDD使用的叫做Gherkin的语言，它的理念是使用自然语言来描述功能，而且强调的是使用例子来说明需求功能。是不是跟敏捷开发中的用户故事(User Story)很像？嗯，因为它们都是一个妈生的。

其实只要我们回顾一下敏捷宣言，就会发现，逼弟弟干的事就是解决个体之间互动与客户协作这两个问题。

> NOTE: 
>
> BDD可以实现敏捷开发

**BDD的需求研讨会(Specification Workshops)**

那么，我们使用这种语言，把需求一个个用例子列出来，客户/产品、开发、测试三方一起讨论与确认。

> NOTE: 
>
> 三方可以同时进行协作，这是BDD的优势

**BDD的由外而内的开发模式(Outside-In Development)**

然后，开发人员使用BDD工具(JBehave, Cucumber, Behave)去运行、实现测试脚本。再一点点编写实现功能代码，走到所有的功能都运行通过。

由于开发的过程是从最接近用户的UI界面开始，再想到内部设计，因此它称为由外而内的开发模式。如果再加上由内而外的过程，嗯，《开发人员的自我修养》就等着你来写了，你叫史坦尼斯拉夫斯基对吧？

回到Gherkin语言，我们上面提到它需要遵循一定的简单语法

-  Scenario(场景)，说明功能的例子
-  Given(假如)，构造测试的环境条件
-  When(当)，给予的输入，可以是用户，也可以是外部系统，也可以是系统本身定时/条件触发的
-  Then(那么)，系统的输出，或者说行为

若干个Given,When,Then构成一个Scenario，若干个Scenario构成一个Feature，若干个Feature最终构成一个系统的完整功能需求。



### [刘文龙的回答](https://www.zhihu.com/question/20161970/answer/14297430)

BDD的核心价值是体现在正确的对系统行为进行设计，所以它并非一种行之有效的测试方法。它强调的是系统最终的实现与用户期望的行为是一致的、验证代码实现是否符合设计目标。但是它本身并不强调对系统功能、性能以及边界值等的健全性做保证，无法像完整的测试一样发现系统的各种问题。但BDD倡导的用简洁的自然语言描述系统行为的理念，可以明确的根据设计产生测试，并保障测试用例的质量。

> NOTE: 
>
> BDD强调的和TDD是不同的
