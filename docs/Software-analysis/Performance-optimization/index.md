# 关于本章

本章讨论performance optimization这个主题的内容。

High performance涉及到发出多的内容，可以说是贯彻了整个computer science。

将从如下几个方面来进行讨论:

1) High performance server

2) Performance optimization in programming language

## Optimization principle

参见文章 《Optimization-principle》。

Optimization principle贯穿了computer science。

## Optimization的方向/how to optimize

下面给出一些optimize的方向，以及如何来实现。

### 避免频繁的system call

tag-avoid-system-call

####  Why system call slow?

参见`./Why-system-call-slow`。


#### How to do?

下面列举一些例子:

1、使用spinning lock，避免kernel将thread suspend，然后thread进入wait/sleeping

2、使用pool design pattern，参见 `Software-design\Design-pattern\Pool`

3、使用lightweight替代方案来替代system call



### Concurrency的优化

parallel computing的崛起，催收concurrent programming，因此concurrency的优化非常重要:

#### How to do?

1、使用non-blocking、lock-less技术。

它们都能够避免进入system call。

2、合理地设计，减少线程竞争

> TODO: 以redis线程模型为例来进行说明，每个thread一个私有的queue，这样有效地避免竞争

### Memory的优化

非常重要的一个方面，其实和前面的内容是有重叠的。并且涉及到的内容是非常多的。

#### How to do?

1、避免copy

tag-avoid-copy

在下面章节中也探讨了这个topic:

a、工程programming language的相关章节

2、避免system call

tag-avoid-system-call-new-malloc

a、SSO

3、string的优化

### Hardware层面的优化

#### How to do?

1、NUMA

2、千兆网卡

3、并发编程



### 将run time computation转移到compile-time

cpp core guideline中有相关的内容



### Algorithm and DS

这在工程discrete中进行讨论；



## Application

1、参见工程programming-language的`C-family\C++\Guide\Performance-optimization`章节。