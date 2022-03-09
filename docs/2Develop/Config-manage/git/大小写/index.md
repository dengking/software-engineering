# git 大小写

windows的文件名是大小写非敏感的，即ignorecase，macOS是大小写敏感的。

## zhihu [Git - 设置大小写敏感](https://zhuanlan.zhihu.com/p/52021994)

**问题：**
本地代码运行ok，但是发现push上去的代码运行后报错，发现有个文件没注意大小写，于是重命名了该文件，发现git没有识别这个更改，不能提交

**查看git 的设置**
`git config --get core.ignorecase`
发现默认是不区分大小的，因此当你修改了文件名的大小写后，git并不会认为你有修改哦
**更改设置**
`git config core.ignorecase false`



## git mv

如果要重命名，需要使用 `git mv`

