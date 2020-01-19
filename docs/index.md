# software engineering

## 编写可以发现问题的代码

对于一些错误情况，程序员需要能够提前断言，然后将这些断言编码到程序中，当此断言成真，即程序进入到了这个分支，需要使用适当的方式通知，不同的编程语言提供了不同的通知方式：

- python可以raise Exception

关于断言，参见：https://en.wikipedia.org/wiki/Assertion_(software_development)

## 管理大工程

作为一个software engineer，管理大型工程是一个合格的软件工程师需要具备的能力，需要研究一些大型的开源软件的管理之道，目前可以参考的有：

- [CPython](https://github.com/python/cpython)
- [Redis](https://github.com/antirez/redis/)





### 工程需要考虑的问题

#### [Software configuration management](https://en.wikipedia.org/wiki/Software_configuration_management)

在软件公司，一般都会有配管的角色。

##### version control 

可以使用的工具：

[git](https://git-scm.com/)

svn

##### build



#### code style

正如python有：

[PEP 7 -- Style Guide for C Code](https://www.python.org/dev/peps/pep-0007/)



#### 设计

系统的interface，比如python，redis等软件，都有着非常好的interface，包括：

- command line interface
- api
- configuration

无论是cpython还是redis，都提供了非常好的interface来探索其内部。