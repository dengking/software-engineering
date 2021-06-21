# 软件工程经验

## 编写可以发现问题的代码

对于一些错误情况，程序员需要能够提前断言，然后将这些断言编码到程序中，当此断言成真，即程序进入到了这个分支，需要使用适当的方式通知，不同的编程语言提供了不同的通知方式：

- python可以raise Exception

关于断言，参见：https://en.wikipedia.org/wiki/Assertion_(software_development)



## [Readability of source code](https://en.wikipedia.org/wiki/Computer_programming#Readability_of_source_code)

如何来保证代码的可读性？

### [Self-documenting code](https://en.wikipedia.org/wiki/Self-documenting_code)

关于self-document code，在阅读[`namedtuple()`](https://docs.python.org/3/library/collections.html#collections.namedtuple) 的文档的时候，看到了它的身影：

> Named tuples assign meaning to each position in a tuple and allow for more readable, **self-documenting code**. They can be used wherever regular tuples are used, and they add the ability to access fields by name instead of position index.





### code style

正如python有：

[PEP 7 -- Style Guide for C Code](https://www.python.org/dev/peps/pep-0007/)



## [Quality requirements](https://en.wikipedia.org/wiki/Computer_programming#Quality_requirements)

