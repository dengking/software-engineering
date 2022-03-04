# git-mechanism



## Git's internal state management system: three tree

1、atlassian [Git Reset](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset)

在这篇文章中提出了，但是理解git three tree 的最好的文章是osteele [My Git Workflow](https://blog.osteele.com/2008/05/my-git-workflow/)，其中给出了非常好的图示

2、osteele [My Git Workflow](https://blog.osteele.com/2008/05/my-git-workflow/)



## The staging area

index=staging index=staging area

### atlassian [Saving changes](https://www.atlassian.com/git/tutorials/saving-changes) # The staging area

The primary function of the `git add` command, is to promote pending changes in the working directory, to the `git staging` area. The staging area is one of Git's more unique features, and it can take some time to wrap your head around it if you’re coming from an SVN (or even a Mercurial) background. It helps to think of it as a buffer between the working directory and the project history. The staging area is considered one of the ["three trees" of Git](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset), along with, the working directory, and the commit history.



## osteele [My Git Workflow](https://blog.osteele.com/2008/05/my-git-workflow/)

Git’s problem is its complexity:

1、Half of that is because it’s actually more powerful than the other systems: it’s got features that make it look scary but that you can ignore. 

2、Another half is that Git uses nonstandard names for about half its most common operations. (The rest of the VCS world has more or less settled on a basic command set, with names such as “checkout” and “revert”. Not Git!) 

3、And the third half is the index. The index is a mechanism for preventing what you commit from matching what you tested in your working directory. Huh?

> NOTE: index就是staging area

### Git without the index

> NOTE:
>
> 简而言之，通过 `git commit -a` 来绕过index

The executive summary of this mode of operation is that if you use “`git commit -a`” instead of “`git commit`”, you can ignore the index altogether. You can alias `ci` to “`commit -a`” (and train yourself not to use the longer `commit`, which I hadn’t been doing anyway), and then you don’t have to remember the command-line argument either:

```sh
$ cat ~/.gitconfig
[alias]
  ci = commit -a
  co = checkout
  st = status -a
$ git ci -m 'some changes'
```

### Adding Back the Index



## stackoverflow [What are the differences between “git commit” and “git push”?](https://stackoverflow.com/questions/2745076/what-are-the-differences-between-git-commit-and-git-push)

In a Git tutorial I'm going through, `git commit` is used to store the changes you've made.

What is `git push` used for then?



#### [A](https://stackoverflow.com/a/2745097)

Basically `git commit` "*records changes to the repository*" while `git push` "*updates remote refs along with associated objects*". So the first one is used in connection with your **local repository**, while the latter one is used to interact with a **remote repository**.

Here is a nice picture from [Oliver Steele](http://blog.osteele.com/2008/05/my-git-workflow/), that explains the git model and the commands:

![Git data transport commands](https://i.stack.imgur.com/MgaV9.png)

> NOTE: 
>
> 一、上述就是three tree，上图其实是源自[Oliver Steele](https://blog.osteele.com/) 的  [My Git Workflow](https://blog.osteele.com/2008/05/my-git-workflow/)



Read more about `git push` and `git pull` on [GitReady.com](http://www.gitready.com/beginner/2009/01/21/pushing-and-pulling.html) (the article I referred to first)

