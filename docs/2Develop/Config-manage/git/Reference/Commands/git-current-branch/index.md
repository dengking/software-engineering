# Git current branch

## stackoverflow [How to get the current branch name in Git?](https://stackoverflow.com/questions/6245570/how-to-get-the-current-branch-name-in-git)



Let your IDE display the file `.git/HEAD`, possibly in a parent directory – [Tino](https://stackoverflow.com/users/490291/tino)  [Feb 4, 2012 at 12:37](https://stackoverflow.com/questions/6245570/how-to-get-the-current-branch-name-in-git#comment11490558_6245570)

[A](https://stackoverflow.com/a/12142066)

To display the current branch you're on, without the other branches listed, you can do the following:

```
git rev-parse --abbrev-ref HEAD
```

Reference:

[Show just the current branch in Git (Sep 2009)](https://stackoverflow.com/a/1418022/367456)



[A](https://stackoverflow.com/a/6245587)

```
git branch
```

should show all the local branches of your repo. The starred branch is your current branch.

If you want to retrieve only the name of the branch you are on, you can do:

```
git rev-parse --abbrev-ref HEAD
```

or with Git 2.22 and above:

```
git branch --show-current
```



[A](https://stackoverflow.com/a/11868440)

You have also `git symbolic-ref HEAD` which displays the full refspec.

To show only the branch name in Git v1.8 and later (thank's to Greg for pointing that out):

```
git symbolic-ref --short HEAD
```

On Git v1.7+ you can also do:

```
git rev-parse --abbrev-ref HEAD
```

Both should give the same branch name if you're on a branch. If you're on a detached head answers differ.

