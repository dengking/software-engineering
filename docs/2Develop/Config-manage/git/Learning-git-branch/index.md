# [learning git branching](https://learngitbranching.js.org/?locale=en)

## branch

```shell
git checkout -b branchname
```

创建并切换到branch。



## Moving around in Git

### HEAD

我们首先看一下 “HEAD”。 HEAD 是一个对当前检出记录的**符号引用** —— 也就是指向你正在其基础上进行工作的提交记录。

HEAD 总是指向当前分支上最近一次提交记录。大多数修改提交树的 Git 命令都是从改变 HEAD 的指向开始的。

HEAD 通常情况下是指向**分支名**的（如 bugFix）。在你提交时，改变了 bugFix 的状态，这一变化通过 HEAD 变得可见。

> NOTE: symbolic reference

```shell
git checkout C1 # C1是commit hash
git checkout main # 检出分支
git commit
git checkout C2 # C1是commit hash
```

（译者注：实际这些命令并不是真的在查看 HEAD 指向，看下一屏就了解了。如果想看 HEAD 指向，可以通过 `cat .git/HEAD` 查看， 如果 HEAD 指向的是一个引用，还可以用 `git symbolic-ref HEAD` 查看它的指向。但是该程序不支持这两个命令）

### 分离的 HEAD

分离的 HEAD 就是让其指向了某个具体的提交记录而不是分支名。在命令执行之前的状态如下所示：

```
HEAD -> main -> C1
```

HEAD 指向 main， main 指向 C1

```shell
git checkout C1
```

现在变成了

```
HEAD -> C1
```

> NOTE: 
>
> 如果查看`.git/HEAD`，会发现其中的内容已经变成了 `C1`。

### 相对引用

通过指定提交记录哈希值的方式在 Git 中移动不太方便。在实际应用时，并没有像本程序中这么漂亮的可视化提交树供你参考，所以你就不得不用 `git log` 来查查看提交记录的哈希值。

并且哈希值在真实的 Git 世界中也会更长（译者注：基于 SHA-1，共 40 位）。例如前一关的介绍中的提交记录的哈希值可能是 `fed2da64c0efc5293610bdd892f82a58e8cbc5d8`。舌头都快打结了吧...

比较令人欣慰的是，Git 对哈希的处理很智能。你只需要提供能够唯一标识提交记录的前几个字符即可。因此我可以仅输入`fed2` 而不是上面的一长串字符。

正如我前面所说，通过哈希值指定提交记录很不方便，所以 Git 引入了相对引用。这个就很厉害了!

使用相对引用的话，你就可以从一个易于记忆的地方（比如 `bugFix` 分支或 `HEAD`）开始计算。

相对引用非常给力，这里我介绍两个简单的用法：

- 使用 `^` 向上移动 1 个提交记录
- 使用 `~<num>` 向上移动多个提交记录，如 `~3`

首先看看操作符 (^)。把这个符号加在引用名称的后面，表示让 Git 寻找指定提交记录的父提交。

所以 `main^` 相当于“`main` 的父节点”。

`main^^` 是 `main` 的第二个父节点

现在咱们切换到 main 的父节点

```shell
git checkout main^
```

> NOTE: 这种方式会移动head

搞定。这种方式是不是比输入哈希值方便多了？！

你也可以将 `HEAD` 作为相对引用的参照。下面咱们就用 `HEAD` 在提交树中向上移动几次。

```sh
git checkout C3;
git checkout HEAD^;
git checkout HEAD^;
git checkout HEAD^;
```

很简单吧？！我们可以一直使用 `HEAD^` 向上移动。

### “~”操作符

如果你想在提交树中向上移动很多步的话，敲那么多 `^` 貌似也挺烦人的，Git 当然也考虑到了这一点，于是又引入了操作符 `~`。

该操作符后面可以跟一个数字（可选，不跟数字时与 `^` 相同，向上移动一次），指定向上移动多少次。咱们还是通过实际操作看一下吧

咱们用 `~<num>` 一次后退四步。

```shell
git checkout HEAD~4
```

多么的简洁 —— 相对引用就是方便啊！

### 强制修改分支位置

你现在是相对引用的专家了，现在用它来做点实际事情。

我使用相对引用最多的就是移动分支。可以直接使用 `-f` 选项让分支指向另一个提交。例如:

```SH
git branch -f main HEAD~3
```

上面的命令会将 main 分支强制指向 HEAD 的第 3 级父提交。

现在咱们来演示一下刚才的命令：

```SH
git branch -f main HEAD~3
```

这就对了! 相对引用为我们提供了一种简洁的引用提交记录 `C1` 的方式， 而 `-f` 则容许我们将分支强制移动到那个位置。

