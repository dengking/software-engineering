# Git Branches



## nobledesktop [Git Branches: List, Create, Switch to, Merge, Push, & Delete](https://www.nobledesktop.com/learn/git/git-branches)

### List All Branches

**NOTE:** The current local branch will be marked with an asterisk (*).

1、To see local branches, run this command:

```sh
git branch
```



2、To see remote branches, run this command:

```sh
git branch -r
```



3、To see all local and remote branches, run this command:

```shell
git branch -a
```



## stackoverflow [How do I delete a Git branch locally and remotely?](https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-locally-and-remotely)



### [A](https://stackoverflow.com/a/2003515/10173843)

#### Executive Summary

```sh
git push -d <remote_name> <branchname> # delete remotely
git branch -d <branchname> # delete locally
```

**Note:** In most cases, `<remote_name>` will be `origin`.

#### Delete Local Branch

```sh
git branch -d <branch_name>
git branch -D <branch_name>
```

1、The `-d` option is an alias for `--delete`, which only deletes the branch if it has already been fully merged in its upstream branch.

2、The `-D` option is an alias for `--delete --force`, which deletes the branch "irrespective of its merged status." [Source: `man git-branch`]

> NOTE: 
>
> "irrespective of" 不管、不顾

3、As of [Git v2.3](https://github.com/git/git/blob/master/Documentation/RelNotes/2.3.0.txt), `git branch -d` (delete) learned to honor the `-f` (force) flag.

4、You will receive an error if you try to delete the currently selected branch.



#### Delete Remote Branch

```shell
git push <remote_name> --delete <branch_name>
```

which might be easier to remember than

```shell
git push <remote_name> :<branch_name>
```

which was added in [Git v1.5.0](https://github.com/gitster/git/blob/master/Documentation/RelNotes/1.5.0.txt) "to delete a remote branch or a tag."

Starting with [Git v2.8.0](https://github.com/git/git/blob/master/Documentation/RelNotes/2.8.0.txt), you can also use `git push` with the `-d` option as an alias for `--delete`. Therefore, the version of Git you have installed will dictate whether you need to use the easier or harder syntax.



> NOTE:
>
> my practice:
>
> ```SHELL
> git push origin --delete feature/litesdk_develop_python_build
> ```
>
> 



## git按创建者来统计分支

### stackoverflow [Is there a script to list git branches created by me?](https://stackoverflow.com/questions/36026374/is-there-a-script-to-list-git-branches-created-by-me)



[A](https://stackoverflow.com/a/36026719/10173843)

```SHELL
git for-each-ref --format=' %(authorname) %09 %(refname)' --sort=authorname 
```

[A](https://stackoverflow.com/a/60037744/10173843)

```SHELL
git branch -r | xargs -L1 git --no-pager show -s --oneline --author="$(git config user.name)"
```



## stackoverflow [Find unmerged Git branches?](https://stackoverflow.com/questions/12276001/find-unmerged-git-branches)





## git create branch with local changes

[Move Existing, Uncommitted Work to a New Branch in Git](https://www.baeldung.com/git-move-uncommitted-work-to-new-branch#:~:text=Using%20the%20git%20checkout%20Command,changes%20to%20the%20new%20branch.&text=There%20is%20no%20local%20change,can%20see%20in%20the%20output.)

> The `git checkout -b <BranchName>` command will create a new branch and switch to it. Moreover, this command will **leave the current branch as it is and bring all uncommitted changes to the new branch**.
