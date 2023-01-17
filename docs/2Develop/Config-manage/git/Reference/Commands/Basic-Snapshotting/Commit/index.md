# git commit





## Squash commits into one



1、CSDN [【git】将多个提交合并为一个commit](https://blog.csdn.net/qq_33237207/article/details/127486804)

2、git-tower [How to Squash Commits in Git](https://www.git-tower.com/learn/git/faq/git-squash)



### zhihu [如何将git的多个commit合成一个了?](https://zhuanlan.zhihu.com/p/507794054)

#### 场景一:

![img](https://pic3.zhimg.com/80/v2-a128ffcb7e8ebd104805432e3b7c8272_1440w.webp)

当我们提交了一个commit 发现完犊子了,打错了刚刚想喷产品没想到打出来了.

这肯定是不行的这个commit肯定是不能push的那我们怎么修改了?

1,很多人肯定想到 `git reset` 一下,这半天的活不就白干了呗.这时候我们有一个命令来修改这个commit.

```shell
git commit --amend
```

这时候就会弹出一个操作框需要会点基本的vim操作

![img](https://pic3.zhimg.com/80/v2-558ae399ed2adb3b39608bc3c0cae59e_1440w.webp)

我们输入 i 进行对commit的修改,当我们改完后输入esc 表示改完了,输入 :wq就可以保存了对吧.

![img](https://pic4.zhimg.com/80/v2-88fea4ad69ada004dfe82e9e20712c97_1440w.webp)

这时候我们再log一下发现就改完了.这样产品看到我们的提交就很开心.

#### 场景二:

我发现我没改完了,还漏了一点但是已经commit 了改完又要commit那不就两个commit了吗?我只想提交一个commit呀.

还是这个命令: 

```shell
git commit --amend --no-edit
```

`--no-edit`就是表示我们不修改了还是和前面那个提交同一个提交.

如图:

![img](https://pic4.zhimg.com/80/v2-0889b6ab76153d17bbf7ed5ba719e56f_1440w.webp)

这样我们就并没有多一次提交.

#### 场景三:

我一不小心提交了,这时候就有两个commit了

![img](https://pic2.zhimg.com/80/v2-90f76e49b978b33b9a018470a38af521_1440w.webp)

那就到我们今天的重点了.

```shell
git rebase -i HEAD~2
```

也可以

```shell
git rebase -i 版本号
```


![img](https://pic1.zhimg.com/80/v2-dae8c67aa4bcfcbc33e0514972168480_1440w.webp)

这时候我们同理输入i 进行编辑 输入完esc退出编辑状态 :wq保存.

其中squash是将两个commit合并成一个提交.

edit是可以编辑提交

这里附上rebase的官网有兴趣的同学可以去看一下

[https://docs.github.com/en/get-started/using-git/about-git-rebase#commands-available-while-](https://link.zhihu.com/?target=https%3A//docs.github.com/en/get-started/using-git/about-git-rebase%23commands-available-while-rebasing)

#### 总结一下:

`git commit --amend` 可以修改提交.

`git rebase -i` 可以将多个提交合并成一个提交.

到时候直接`git push -f` 强推一下就好了.

### see also

stackoverflow [How do I squash my last N commits together?](https://stackoverflow.com/questions/5189560/how-do-i-squash-my-last-n-commits-together)