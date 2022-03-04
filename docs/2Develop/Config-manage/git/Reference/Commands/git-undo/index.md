# Git undo

[git](https://git-scm.com/)是一个version control工具，在version control中一些常见的操作就是revert/undo：

1、revert files back to a previous state

2、revert the entire project back to a previous state



## gitlab [Numerous undo possibilities in Git](https://docs.gitlab.com/ee/topics/git/numerous_undo_possibilities_in_git/)





## 分类

### discard unstaged change

`git status` 的输出: 

```sh
On branch develop
Your branch is ahead of 'origin/develop' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
  (commit or discard the untracked or modified content in submodules)
	modified:   ../.gitignore
	modified:   ../thirdparty/WebRTC (new commits, modified content)

no changes added to commit (use "git add" and/or "git commit -a")
```

显然，它给出了suggestion: `use "git restore <file>..." to discard changes in working directory` 。



#### stackoverflow [How do I discard unstaged changes in Git?](https://stackoverflow.com/questions/52704/how-do-i-discard-unstaged-changes-in-git)

[A](https://stackoverflow.com/a/12184274)

> NOTE:
>
> 这个回答是比较精炼的

It seems like the complete solution is:

```SH
git clean -df
git checkout -- .
```

[`git clean`](https://git-scm.com/docs/git-clean) removes all untracked files (**warning**: while it won't delete ignored files mentioned directly in .gitignore, **it may delete ignored files residing in folders**) and `git checkout` clears all unstaged changes.

[A](https://stackoverflow.com/a/52713)

For all unstaged files in current working directory use:

```SHELL
git checkout -- .
```

For a specific file use:

```shell
git checkout -- path/to/file/to/revert
```

`--` here to remove ambiguity (this is known as [argument disambiguation](https://git-scm.com/docs/git-checkout#_argument_disambiguation)).

For Git 2.23 onwards, one may want to use the more specific

```shell
git restore .
```

resp.

```shell
git restore path/to/file/to/revert
```

that together with `git switch` replaces the overloaded `git checkout` ([see here](https://stackoverflow.com/questions/58003030/what-is-the-git-restore-command-and-what-is-the-difference-between-git-restor)), and thus removes the argument disambiguation.



### removes untracked files fromworking tree

在 stackoverflow [How do I discard unstaged changes in Git?](https://stackoverflow.com/questions/52704/how-do-i-discard-unstaged-changes-in-git) 的comment中，有如下内容:

> 1、`git-clean` only removes untracked files from the working tree [git-scm.com/docs/git-clean](https://git-scm.com/docs/git-clean) – [Yega](https://stackoverflow.com/users/1661299/yega)  [Sep 15, 2016 at 12:29](https://stackoverflow.com/questions/52704/how-do-i-discard-unstaged-changes-in-git#comment66338004_52704)
>
> 2、To clarify Asenar's comment above, `git-clean -df` can be dangerous. It will delete local untracked files (e.g. covered by a .gitignore) Read all below carefully and consider git checkout . instead – [jacanterbury](https://stackoverflow.com/users/765827/jacanterbury)  [Oct 7, 2016 at 8:05](https://stackoverflow.com/questions/52704/how-do-i-discard-unstaged-changes-in-git#comment67109097_52704) 

## 素材

stackoverflow [How do I revert a Git repository to a previous commit?](https://stackoverflow.com/questions/4114095/how-do-i-revert-a-git-repository-to-a-previous-commit)



stackoverflow [How do I undo the most recent local commits in Git?](https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git)



stackoverflow [Rollback to an old Git commit in a public repo](https://stackoverflow.com/questions/2007662/rollback-to-an-old-git-commit-in-a-public-repo)



github.blog [How to undo (almost) anything with Git](https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/)



opensource [How to reset, revert, and return to previous states in Git](https://opensource.com/article/18/6/git-reset-revert-rebase-commands)



stackoverflow [How to get back to most recent version in Git?](https://stackoverflow.com/questions/3559076/how-to-get-back-to-most-recent-version-in-git)

