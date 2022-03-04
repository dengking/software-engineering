# Behavior-driven development(BDD)



## zhihu [TDD 与 BDD 仅仅是语言描述上的区别么？](https://www.zhihu.com/question/20161970)

> NOTE: 
>
> 其中进行了非常好的探讨



### [刘文龙的回答](https://www.zhihu.com/question/20161970/answer/14297430)

BDD的核心价值是体现在正确的对系统行为进行设计，所以它并非一种行之有效的测试方法。它强调的是系统最终的实现与用户期望的行为是一致的、验证代码实现是否符合设计目标。但是它本身并不强调对系统功能、性能以及边界值等的健全性做保证，无法像完整的测试一样发现系统的各种问题。但BDD倡导的用简洁的自然语言描述系统行为的理念，可以明确的根据设计产生测试，并保障测试用例的质量。

### [程序人生的回答](https://www.zhihu.com/question/20161970/answer/1341811526)

> NOTE: 
>
> 这个回答非常好，基本上将清除了BDD，并且结合非常好的例子，已经收录了。

## wanweibaike [Behavior-driven development](https://en.wanweibaike.com/wiki-Behavior-driven%20development)

In [software engineering](https://en.wanweibaike.com/wiki-Software_engineering), **behavior-driven development** (**BDD**) is an [agile software development](https://en.wanweibaike.com/wiki-Agile_software_development) process that encourages collaboration among developers, quality assurance testers, and customer representatives in a software project.

> NOTE: 
>
> 一、**developers**, **quality assurance testers**, **customer representatives** 三者一同进行协作

It encourages teams to use conversation and concrete examples to formalize a shared understanding of how the application should behave.[[4\]](https://en.wanweibaike.com/wiki-Behavior-driven development#cite_note-BDD_in_action-4) 

> NOTE: 
>
> 一、场景化

It emerged from [test-driven development](https://en.wanweibaike.com/wiki-Test-driven_development) (TDD). Behavior-driven development combines the general techniques and principles of TDD with ideas from [domain-driven design](https://en.wanweibaike.com/wiki-Domain-driven_design) and [object-oriented analysis and design](https://en.wanweibaike.com/wiki-Object-oriented_analysis_and_design) to provide software development and management teams with shared tools and a shared process to collaborate on software development.

> NOTE: 
>
> 一、源自TDD，弥补其不足
>
> 二、通过上面再次强调了"**developers**, **quality assurance testers**, **customer representatives** 三者一同进行协作"，其实这实现了敏捷开发的目的，正如 zhihu [TDD 与 BDD 仅仅是语言描述上的区别么？](https://www.zhihu.com/question/20161970) # [程序人生的回答](https://www.zhihu.com/question/20161970/answer/1341811526) 中所述:
>
> > ```
> > Scenario: Refunded items should be returned to stock
> >   Given a customer bought a black sweater from me
> >     and I have three black sweaters left in stock.
> >    When he returns the sweater for a refund
> >    then I should have four black sweaters in stock.
> > 
> > 
> > 场景： 微信聊天
> > 假如  手机安装了微信
> > 当  用户打开微信
> > 那么  手机会出现用户的微信聊天界面
> > ```
> >
> > 以上就是BDD使用的叫做Gherkin的语言，它的理念是使用自然语言来描述功能，而且强调的是使用例子来说明需求功能。是不是跟敏捷开发中的用户故事(User Story)很像？嗯，因为它们都是一个妈生的。
> >
> > 其实只要我们回顾一下敏捷宣言，就会发现，逼弟弟干的事就是解决个体之间互动与客户协作这两个问题。
> >
> > 



## software [Cucumber](https://cucumber.io/)

这个软件将BDD从理论带入了工程实践中。

