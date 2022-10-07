# git



## THINKING

### repositories 中包含哪些内容？

应该按照层次来进行描述：

从[GitHub Flow](#GitHub Flow ) 中可以看出，git中的第一级结构就是**branch**，也就是说，一个repository包含多个branch，不同branch之间应该是相互隔离的，如果要进行类比的话，branch之于git就相当于process之于operating system：

1、基于一个branch构造一个新的branch，就相当于`fork`系统调用



### local repository  AND  remote repository 

remote repository一般就是GitHub，显然管理local repository和remote repository是git的一个非常重要的部分：

1、synchronization同步



### git中的角色与权限

显然，每个repository需要记录下它是由谁创建的，即它的**主人**是谁。一般在多人协作进行开发的时候，显然不同的角色是有不同的**权限**的，那git中是否也是如此呢？如果是这样的话，git中有哪些**角色**和**权限**？



## 资源

1、[Git Cheat Sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf) 

2、[bitbucket tutorial](https://www.atlassian.com/git/tutorials)

