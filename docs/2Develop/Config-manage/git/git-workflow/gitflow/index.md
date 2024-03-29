# gitflow



## Git 工作流

> NOTE: 
>
> 一、网易采用的就是这种
>
> 二、它本质上是branch model

新仓库的 Git 工作流采用 git flow，简单来说 master 分支作为当前**最新稳定**代码分支。新的版本迭代过程中，我们基于 `develop` 开出新的 `feature/*` 分支进行功能开发，当**冒烟测试**稳定后合并至 `develop` 分支。在一个版本所有 `feature/*` 分支都合并到 `develop` 准备**集成测试**时，基于 `develop` 开出 `release/*` 分支（星号代表发布版本号），**回归**完成后合并 `release/*` 到 `develop` 和 `master` 并按版本号创建一个最新的 tag。

> NOTE: 
>
> 集成测试是基于`release/*` 分支

对于 git flow 工作流有任何问题请参考以下内容：

1、nvie [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)

> NOTE:
>
> 一、git-flow就是由这篇文章的作者 [Vincent Driessen](https://nvie.com/about/) 提出，这是在阅读 [Fork for Windows 1.17](https://fork.dev/blog/posts/forkwin-1.17/) 时，其中有这样的一段话:
>
> "Git Flow is a well established workflow for git repositories made popular by [a post by Vincent Driessen](https://nvie.com/posts/a-successful-git-branching-model/). "

2、atlassian [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

任何打乱 git flow 工作流的行为都可能会造成仓库分支混乱、合并冲突等问题，如您的分支命名方式不是以 git flow 方式创建，将会导致 CI 在编译时无法获取正确的分支、版本等信息。或您开启新的分支并不是以 git flow 规定的方式创建将会导致一系列代码合并错误。

建议使用 [git-flow](https://github.com/nvie/gitflow) 命令行终端来做日常的开发而不是原生 git 指令来开启或合并分支。或使用集成了 git flow 工作流的客户端如 [SourceTree](https://www.sourcetreeapp.com/)、[SmartGit](https://www.syntevo.com/smartgit/) 等，这些客户端天然集成了通过 UI 来创建 feature、release、hotfix 等能力可以减少协同开发过程中的错误。

对版本号的管理，我们遵循 [Semantic Versioning 2.0.0](https://semver.org/lang/zh-CN/)



## git-tower [Workflows with git-flow](https://www.git-tower.com/learn/git/ebook/en/command-line/advanced-topics/git-flow)



## Practice

一、git-tower [Workflows with git-flow](https://www.git-tower.com/learn/git/ebook/en/command-line/advanced-topics/git-flow)

![](./hotfix.jpg)

```shell
git checkout Tags/0.3.0 # 必须首先checkout这个tag
git flow hotfix start 0.3.1
# 在 hotfix 分支做修改，测试，确认没问题后
git flow hotfix finish 0.3.1
```

