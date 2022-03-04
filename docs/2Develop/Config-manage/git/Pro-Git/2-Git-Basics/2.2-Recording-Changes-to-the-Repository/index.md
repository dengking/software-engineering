# [2.2 Git Basics - Recording Changes to the Repository](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)

## Recording Changes to the Repository

Remember that each file in your working directory can be in one of two states: *tracked* or *untracked*. 

> NOTE: 
>
> 一、file state:
>
> 1、untracked
>
> 2、tracked:
>
> a、modified
>
> b、unmodified
>
> c、staged
>
> 

![The lifecycle of the status of your files](https://git-scm.com/book/en/v2/images/lifecycle.png)

Figure 8. The lifecycle of the status of your files

> NOTE: 
>
> 一、在[1.3 Getting Started - What is Git?](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F)节、[2.2 Git Basics - Recording Changes to the Repository](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)节中都有描述git的文件状态的变化，这些都是可以使用state machine来进行建模刻画的。
>
> 上述是典型的state machine

### Checking the Status of Your Files

> NOTE: 
>
> 主要是git status命令

```shell
git status
```



### Tracking New Files

```shell
git add README
```

### Staging Modified Files

```shell
git add CONTRIBUTING.md
```

### Short Status

> NOTE: 
>
> 这一段内容非常重要



## 补充内容: staging area

'staging area'即 '集结区'

https://en.wikipedia.org/wiki/Staging_area

### stackoverflow [What's the use of the staging area in Git?](https://stackoverflow.com/questions/49228209/whats-the-use-of-the-staging-area-in-git)



### git [About # Staging Area](https://git-scm.com/about/staging-area)

![Index 1](https://git-scm.com/images/about/index1@2x.png)