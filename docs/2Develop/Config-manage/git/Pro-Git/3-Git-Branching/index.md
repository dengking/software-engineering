# [3 Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)

关于git的branch，在这些地方有所阐述：

在 [About # Branching and Merging](https://git-scm.com/about) 中：

> Git allows and encourages you to have multiple local branches that can be entirely independent of each other. The creation, merging, and deletion of those lines of development takes seconds.

git的设计者鼓励的做法是使用branch，至于为什么这样？后面会给出答案。

在[1.2 Getting Started - A Short History of Git](https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git) 中:
> Strong support for non-linear development (thousands of parallel branches)

所谓"non-linear development"其实就是多个branch的并行，在软件工程开发中，这种non-linear development是在开发过程中普遍存在的一种workflow，比如在 [About # Branching and Merging](https://git-scm.com/about) 中枚举的**Feature Based Workflow**就是一种non-linear development。

在[chapter 3 Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)中：

> Some people refer to Git’s branching model as its “killer feature,” and it certainly sets Git apart in the VCS community.

那git branch的价值何在呢？

在 [About # Branching and Merging](https://git-scm.com/about) 中对此进行了总结：

1、**Role-Based Codelines**. Have a branch that always contains only what goes to **production**, another that you merge work into for **testing**, and several smaller ones for day to day **work**.

> NOTE: 软件工程中有[Development, testing, acceptance and production](https://en.wikipedia.org/wiki/Development,_testing,_acceptance_and_production)的基本流程，上面这段中的work对应的是development。

2、**Feature Based Workflow**. Create new branches for each new feature you're working on so you can seamlessly switch back and forth between them, then delete each branch when that feature gets merged into your main line.

> NOTE: 这就是在在[1.2 Getting Started - A Short History of Git](https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git)中所述的non-linear development。

3、**Disposable Experimentation**. Create a branch to experiment in, realize it's not going to work, and just delete it - abandoning the work—with nobody else ever seeing it (even if you've pushed other branches in the meantime).

上述这些是在软件工程中非常需要的功能。

