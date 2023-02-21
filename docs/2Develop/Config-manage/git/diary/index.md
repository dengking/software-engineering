# git merge a range of commit

## stackoverflow [How to cherry-pick a range of commits and merge them into another branch?](https://stackoverflow.com/questions/1994463/how-to-cherry-pick-a-range-of-commits-and-merge-them-into-another-branch)



### [A](https://stackoverflow.com/a/1994491)

When it comes to a range of commits, cherry-picking ~~is~~ *was* not practical.



---

#### Original answer (January 2010)

A `rebase --onto` would be better, where you **replay** the given range of commit on top of your **integration branch**, as [Charles Bailey described here](https://stackoverflow.com/questions/509859/what-is-the-best-way-to-git-patch-a-subrange-of-a-branch).



## stackoverflow [What is the best way to git patch a subrange of a branch?](https://stackoverflow.com/questions/509859/what-is-the-best-way-to-git-patch-a-subrange-of-a-branch)



### [A](https://stackoverflow.com/a/510453)

The easiest way to perform the action that you are looking for is with `git rebase`. Here's a recipe(菜谱、诀窍). Assume that tag `A` is the commit on top of which the patch series that you want to select is based and that tag `B` is the commit of the final patch in the series. Also, assume that `br` is the name of the **current branch** and the branch where the new patch series should be applied.

```sh
# Checkout a new temporary branch at the current location
git checkout -b tmp

# Move the br branch to the head of the new patchset
git branch -f br B

# Rebase the patchset onto tmp, the old location of br
git rebase --onto tmp A br
```



### [A](https://stackoverflow.com/a/8678190)

The easiest way I've found to do this is:

```sh
git cherry-pick starthash..endhash
```

Note that the two dots have no spaces separating them from the hash labels. Also, this will not cherry-pick `starthash`, but rather everything after `starthash` up to and including `endhash`. To include `starthash` do `git cherry-pick starthash^..endhash`.



# git parent



## stackoverflow [How to find the nearest parent of a Git branch](https://stackoverflow.com/questions/3161204/how-to-find-the-nearest-parent-of-a-git-branch)



[A](https://stackoverflow.com/a/52025740)

> NOTE:
>
> 试了这种方法，可行

