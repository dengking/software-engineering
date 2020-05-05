# [12factor](https://12factor.net/zh_cn/)

# Introduction

In the modern era, software is commonly delivered as a service: called *web apps*, or *software-as-a-service*. The twelve-factor app is a methodology for building software-as-a-service apps that:

- Use **declarative** formats for **setup automation**(使用声明性格式进行设置自动化), to minimize time and cost for new developers joining the project;
- Have a **clean contract** with the underlying operating system, offering **maximum portability** between execution environments;
- Are suitable for **deployment** on modern **cloud platforms**, obviating the need for servers and systems administration;
- **Minimize divergence** between development and production, enabling **continuous deployment** for maximum agility(降低development和production之间的差异，实现持续部署以实现最大灵活性);
- And can **scale up** without significant changes to tooling, architecture, or development practices(并且可以在不对工具，体系结构或开发实践进行重大更改的情况下进行扩展).

The **twelve-factor methodology** can be applied to apps written in any programming language, and which use any combination of backing services (database, queue, memory cache, etc).

# Background

The contributors to this document have been directly involved in the development and deployment of hundreds of apps, and indirectly witnessed the development, operation, and scaling of hundreds of thousands of apps via our work on the [Heroku](http://www.heroku.com/) platform.

This document synthesizes(综合) all of our experience and observations on a wide variety of software-as-a-service apps in the wild. It is a triangulation(三角) on **ideal practices**(理想实践) for app development, paying particular attention to the dynamics of the organic growth of an app over time(特别关注应用程序随着时间推移的有机增长动态), the dynamics of collaboration between developers working on the app’s codebase(开发应用程序代码库的开发人员之间的协作动态，以及避免成本 软件侵蚀), and [avoiding the cost of software erosion](http://blog.heroku.com/archives/2011/6/28/the_new_heroku_4_erosion_resistance_explicit_contracts/).

Our motivation is to raise awareness of some systemic problems we’ve seen in modern application development, to provide a shared vocabulary for discussing those problems, and to offer a set of broad conceptual solutions to those problems with accompanying terminology. The format is inspired by Martin Fowler’s books *Patterns of Enterprise Application Architecture* and *Refactoring*.

# Who should read this document?

Any developer building applications which run as a service. Ops engineers who deploy or manage such applications.

# The Twelve Factors

## [I. Codebase](https://12factor.net/codebase)

### One codebase tracked in revision control, many deploys

使用版本控制系统进行跟踪的codebase。

总结：这段描述了这三者之间的关系：app，code repo，deploy，codebase

A twelve-factor app is always tracked in a **version control system**, such as [Git](http://git-scm.com/), [Mercurial](https://www.mercurial-scm.org/), or [Subversion](http://subversion.apache.org/). A copy of the **revision tracking database** is known as a *code repository*, often shortened to *code repo* or just *repo*.

A *codebase* is any single repo (in a centralized revision control system like Subversion)(代码库是任何单个仓库), or any set of repos who share a root commit (in a decentralized revision control system like Git).



![One codebase maps to many deploys](https://12factor.net/images/codebase-deploys.png)

There is always a one-to-one correlation between the codebase and the app(代码库和应用程序之间始终存在一对一的关联):

- If there are multiple codebases, it’s not an app – it’s a distributed system(如果有多个代码库，它不是一个应用程序 - 它是一个分布式系统). Each component in a distributed system is an app, and each can individually comply with twelve-factor.
- Multiple apps sharing the same code is a violation of twelve-factor. The solution here is to factor(分解) shared code into libraries which can be included through the [dependency manager](https://12factor.net/dependencies).

There is only one codebase per app, but there will be many deploys of the app(每个应用程序只有一个代码库，但应用程序的部署将很多). A **deploy** is a running instance of the app. This is typically a production site, and one or more staging sites(临时站点). Additionally, every developer has a copy of the app running in their local development environment, each of which also qualifies as a **deploy**.

The codebase is the same across all deploys, although different versions may be active in each deploy. For example, a developer has some commits not yet deployed to staging; staging has some commits not yet deployed to production. But they all share the same codebase, thus making them identifiable as different deploys of the same app.

## [II. Dependencies](https://12factor.net/dependencies)

### Explicitly declare and isolate dependencies

## [III. Config](https://12factor.net/config)

### Store config in the environment

## [IV. Backing services](https://12factor.net/backing-services)

### Treat backing services as attached resources

## [V. Build, release, run](https://12factor.net/build-release-run)

### Strictly separate build and run stages

## [VI. Processes](https://12factor.net/processes)

### Execute the app as one or more stateless processes

## [VII. Port binding](https://12factor.net/port-binding)

### Export services via port binding

## [VIII. Concurrency](https://12factor.net/concurrency)

### Scale out via the process model

## [IX. Disposability](https://12factor.net/disposability)

### Maximize robustness with fast startup and graceful shutdown

## [X. Dev/prod parity](https://12factor.net/dev-prod-parity)

### Keep development, staging, and production as similar as possible

## [XI. Logs](https://12factor.net/logs)

### Treat logs as event streams

## [XII. Admin processes](https://12factor.net/admin-processes)

### Run admin/management tasks as one-off processes
