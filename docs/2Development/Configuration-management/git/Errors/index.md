# Cannot lock ref 'refs/remotes/origin/master' 



## github [desktop](https://github.com/desktop)/**[desktop](https://github.com/desktop/desktop)**/[Error: Cannot lock ref 'refs/remotes/origin/master' #6121](https://github.com/desktop/desktop/issues/6121)

### [A](https://github.com/desktop/desktop/issues/6121#issuecomment-437145964)

```shell
rm .git/refs/remotes/origin/master
git fetch
git branch --set-upstream-to=origin/master
```

> NOTE: 
>
> 能够成功解决问题

Let me know if that doesn't get things working.

## stackoverflow [cannot lock ref 'refs/remotes/origin/master'](https://stackoverflow.com/questions/58126421/cannot-lock-ref-refs-remotes-origin-master)



### A

```shell
$ git update-ref -d refs/remotes/origin/[locked branch name]
```

> NOTE: 
>
> 并没有用