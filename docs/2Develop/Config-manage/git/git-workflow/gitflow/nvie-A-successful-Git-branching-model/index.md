# nvie [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)

> NOTE:
>
> 一、git-flow就是由这篇文章的作者 [Vincent Driessen](https://nvie.com/about/) 提出，这是在阅读 [Fork for Windows 1.17](https://fork.dev/blog/posts/forkwin-1.17/) 时，其中有这样的一段话:
>
> "Git Flow is a well established workflow for git repositories made popular by [a post by Vincent Driessen](https://nvie.com/posts/a-successful-git-branching-model/). "



## Note of reflection (March 5, 2020)

> NOTE:
>
> 一、在这一段作者所要表达的观点是: 不要迷信教条(dogma)，包治百病的灵丹妙药(panacea)是不存在的，要选择适合于自己团队的workflow。

This model was conceived in 2010, now more than 10 years ago, and not very long after Git itself came into being. In those 10 years, git-flow (the branching model laid out in this article) has become hugely popular in many a software team to the point where people have started treating it like a standard of sorts — but unfortunately also as a dogma or panacea.

> NOTE：
>
> 一、翻译如下:
>
> "这个模型是在 2010 年构想出来的，现在已经是 10 多年前了，也就是 Git 本身出现后不久。在这 10 年里，git-flow（本文中介绍的分支模型）在许多软件团队中变得非常流行，以至于人们开始将其视为某种标准——但不幸的是，它也被视为一种教条或灵丹妙药."

During those 10 years, Git itself has taken the world by a storm, and the most popular type of software that is being developed with Git is shifting more towards web apps — at least in my filter bubble. Web apps are typically continuously delivered, not rolled back, and you don't have to support multiple versions of the software running in the wild.

This is not the class of software that I had in mind when I wrote the blog post 10 years ago. If your team is doing continuous delivery of software, I would suggest to adopt a much simpler workflow (like [GitHub flow](https://guides.github.com/introduction/flow/)) instead of trying to shoehorn git-flow into your team.

> NOTE:
>
> 一、对于web application，由于它是CI的、不需要roll back的，因此它是不需要multiple version的，因此对于这种software，可以采用简单的workflow:   [GitHub flow](https://guides.github.com/introduction/flow/) 

If, however, you are building software that is explicitly versioned, or if you need to support multiple versions of your software in the wild, then git-flow may still be as good of a fit to your team as it has been to people in the last 10 years. In that case, please read on.

To conclude, always remember that panaceas don't exist. Consider your own context. Don't be hating. Decide for yourself.

> NOTE:
>
> 一、包治百病的灵丹妙药是不存在的。

## 正文

I won’t talk about any of the projects’ details, merely about the branching strategy and release management.

![img](https://nvie.com/img/git-model@2x.png)

## Why git? [¶](https://nvie.com/posts/a-successful-git-branching-model/#why-git)

> NOTE:
>
> 一、这一段所探讨的是: git的"branching and merging"

## The main branches [¶](https://nvie.com/posts/a-successful-git-branching-model/#the-main-branches)

The central repo holds two main branches with an infinite lifetime:

1、`master`

2、`develop`



## Supporting branches [¶](https://nvie.com/posts/a-successful-git-branching-model/#supporting-branches)

The different types of branches we may use are:

1、Feature branches

2、Release branches

3、Hotfix branches

