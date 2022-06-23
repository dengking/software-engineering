# git submodule



在git的具体实现中，使用文件 `.gitmodules` 保存它的所有的submodule。



```shell
git submodule update --init --recursive -j 5
```



在parent repository中，记录的本质上是submodule 的 HEAD 这个**符合名称**，因此只要拿到HEAD，那么在**子模块**中，无论是切换分支、commit修改、移动HEAD，parent都能够按图索骥拿到最新的修改，这就是它的实现原理。

目前git并不支持在parent repository中指定submodule的commit hash，只能够通过修改子模块来进行实现。



## 素材

git-scm doc [7.11 Git Tools - Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) 

atlassian [Git submodules](https://www.atlassian.com/git/tutorials/git-submodule)



## devconnected [How To Add and Update Git Submodules](https://devconnected.com/how-to-add-and-update-git-submodules/)

> NOTE: 
>
> 这篇文章非常好

In this tutorial, we are going to explain **how you can easily add, update and remove Git submodules on your main project.**

### Add a Git Submodule

```shell
git submodule add <remote_url> <destination_folder>
```

> NOTE: 
>
> 我的练习:
>
> ```shell
> git submodule add https://github.com/dengking/practice-git-2.git submodules
> ```
>
> 



### Pull a Git Submodule

```shell
git submodule update --init --recursive
```



## stackoverflow [How can I specify a branch/tag when adding a Git submodule?](https://stackoverflow.com/questions/1777854/how-can-i-specify-a-branch-tag-when-adding-a-git-submodule)

> NOTE:
>
> 如何指定submodule的commit hash？

[A](https://stackoverflow.com/a/18797720/10173843)



## stackoverflow [How to see which commit a git submodule points at](https://stackoverflow.com/questions/20655073/how-to-see-which-commit-a-git-submodule-points-at)