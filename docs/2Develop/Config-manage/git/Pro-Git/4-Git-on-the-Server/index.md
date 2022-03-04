# 4. [Git on the Server](https://git-scm.com/book/en/v2/Git-on-the-Server-The-Protocols)

## [4.1 Git on the Server - The Protocols](https://git-scm.com/book/en/v2/Git-on-the-Server-The-Protocols)

> NOTE: 
>
> 本节描述如何创建一个git server，并且指定它们支持的protocol

Git can use four distinct protocols to transfer data: Local, HTTP, Secure Shell (SSH) and Git. Here we’ll discuss what they are and in what basic circumstances you would want (or not want) to use them.

## [4.3 Git on the Server - Generating Your SSH Public Key](https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key)

Many Git servers authenticate using SSH public keys. 

> NOTE: 
>
> 使用public key的优势是无需每次都输入用户名和命名

The `.pub` file is your public key, and the other file is the corresponding private key. If you don’t have these files (or you don’t even have a `.ssh` directory), you can create them by running a program called `ssh-keygen`, which is provided with the SSH package on Linux/macOS systems and comes with Git for Windows

> NOTE: 
>
> 上面提到了public key、private key的概念



First it confirms where you want to save the key (`.ssh/id_rsa`), and then it asks twice for a passphrase, which you can leave empty if you don’t want to type a password when you use the key. However, if you do use a password, make sure to add the `-o` option; it saves the private key in a format that is more resistant to brute-force password cracking than is the default format. You can also use the `ssh-agent` tool to prevent having to enter the password each time.

> NOTE: 
>
> 一、"passphrase"的意思是"密码; 私钥密码; 密语; 口令短语; 通行码"，此处它的含义是 "私钥密码"



### 补充内容

原文仅仅介绍了如何生成public key，但是并没有详细介绍如何使用public key，下面是一些补充内容:

cnblogs [Git SSH公钥配置](https://www.cnblogs.com/yangshifu/p/9919817.html)

csdn [Git使用手册/Git教程：使用SSH Key及配置SSH key公钥](https://blog.csdn.net/u013374164/article/details/78423342)



csdn [git---如何解决The authenticity of host 'github.com (192.30.255.112)' can't be established.](https://blog.csdn.net/Wbiokr/article/details/73431199)

> NOTE: 
>
> 按照这篇文章中的做法成功解决了问题