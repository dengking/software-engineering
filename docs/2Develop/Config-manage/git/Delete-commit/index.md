# Delete commit

1、delete commit from local

2、delete commit from remote

素材:

1、stackoverflow [Throw away local commits in Git](https://stackoverflow.com/questions/5097456/throw-away-local-commits-in-git)

2、stackoverflow [Various ways to remove local Git changes](https://stackoverflow.com/questions/22620393/various-ways-to-remove-local-git-changes)

3、stackoverflow [Delete commits from a branch in Git](https://stackoverflow.com/questions/1338728/delete-commits-from-a-branch-in-git)



## Delete commit locally

### stackoverflow [Throw away local commits in Git](https://stackoverflow.com/questions/5097456/throw-away-local-commits-in-git)



#### [A](https://stackoverflow.com/a/5097495)

If your excess commits are only visible to you, you can just do `git reset --hard origin/<branch_name>` to move back to where the origin is. This will reset the state of the repository to the previous commit, and it will discard all local changes.

> NOTE:
>
> 上述 `origin/<branch_name>` 是典型的引用remote branch的方式

Doing a `git revert` makes *new* commits to remove *old* commits in a way that keeps everyone's history sane.

> NOTE: 
>
> 一、"sane"的意思是理智的
>
> 二、my practice:
>
> ```shell
> git reset --hard origin/main
> ```



comments:

`git reset --hard <commit hash, branch, or tag>` if you want to go to a specific reference other than a remote branch. – [Sam Soffe](https://stackoverflow.com/users/118631/sam-soffes)

> NOTE:
>
> 上面这段话其实概括了git reset 的用法



## stackoverflow [Delete commits from a branch in Git](https://stackoverflow.com/questions/1338728/delete-commits-from-a-branch-in-git)

[A](https://stackoverflow.com/a/1338744)

```
git reset --hard HEAD~1
```

```
git reset --hard <sha1-commit-id>
```

```
git push origin HEAD --force
```

If you already pushed, it may be better to use `git revert`, to create a "mirror image" commit that will undo the changes. However, both commits will be in the log.

