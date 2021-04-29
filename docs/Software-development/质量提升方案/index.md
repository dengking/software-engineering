# 软件质量提升方案、科学的软件工程方法

## 前言

一、本文论述如何系统的提升软件质量，会涉及软件工程的一些理论知识，同时本文还会描述如何应用于我们的项目、如何实现、介绍一些常用工具及其功能、使用方法等；

二、成功的软件项目能够给我们提供很多的软件工程经验，因此，本文参考了GitHub上一些比较成熟的开源软件，包括:

1、[nlohmann](https://github.com/nlohmann)/**[json](https://github.com/nlohmann/json)**

这个软件比较成熟，它采用的软件工程方法是比较典型的，值得借鉴；它使用C++11开发，在GitHub上有24.2K的star，说明它是比较受欢迎的



## 经验与反思

1、一个好的programmer，首先需要是一个好的QA、tester

2、测试没有提缺陷并不代表软件质量好，没有bug

3、一些隐藏的bug，一旦爆发，不仅难以排除，后果可能非常严重（比如之前在POC的时候，发生了 integer overflow undefined behavior，导致的问题非常诡异，排查起来非常困难，如果经验不丰富，则根本无从查起，需要考虑如何系统性地解决这类问题）

4、需要借助tool来分析程序，找出常见bug

> NOTE: 
>
> 1、tool非常多，合理的使用tool，能够发现潜在的bug

5、规范，避免常见bug





## 案例: [nlohmann](https://github.com/nlohmann)/**[json](https://github.com/nlohmann/json)**

> NOTE: 
>
> 1、
>
> 

### build

> NOTE:
>
> 1、自动化集成、CI (我们有)

[![Build Status](https://camo.githubusercontent.com/81db7525de1c004a7d307a558e5082e0be7bc9daca17ad3034713097d8158bbd/68747470733a2f2f7472617669732d63692e6f72672f6e6c6f686d616e6e2f6a736f6e2e7376673f6272616e63683d6d6173746572)](https://travis-ci.org/nlohmann/json) 

[![Build Status](https://camo.githubusercontent.com/90c82594e7c265f72a5636532f48c280e53233e95d1fe27b404285ae5de3ce4b/68747470733a2f2f63692e6170707665796f722e636f6d2f6170692f70726f6a656374732f7374617475732f3161636233363678667967337179626b2f6272616e63682f646576656c6f703f7376673d74727565)](https://ci.appveyor.com/project/nlohmann/json) 

[![Ubuntu](https://github.com/nlohmann/json/workflows/Ubuntu/badge.svg)](https://github.com/nlohmann/json/actions?query=workflow%3AUbuntu) 

[![macOS](https://github.com/nlohmann/json/workflows/macOS/badge.svg)](https://github.com/nlohmann/json/actions?query=workflow%3AmacOS) 

[![Windows](https://github.com/nlohmann/json/workflows/Windows/badge.svg)](https://github.com/nlohmann/json/actions?query=workflow%3AWindows) 



### 代码覆盖率

> NOTE:
>
> 1、我们没有

[![Coverage Status](https://camo.githubusercontent.com/39ee96886bedc0790ac04b78a42014e98c725911207c5b0ddf40b084c41ce3e1/68747470733a2f2f636f766572616c6c732e696f2f7265706f732f6769746875622f6e6c6f686d616e6e2f6a736f6e2f62616467652e7376673f6272616e63683d646576656c6f70)](https://coveralls.io/github/nlohmann/json?branch=develop) 

[![Coverity Scan Build Status](https://camo.githubusercontent.com/b707b103c9d903b5cf587dd7e3b3e88d049d32c6234aac45f8322861b2bb563a/68747470733a2f2f7363616e2e636f7665726974792e636f6d2f70726f6a656374732f353535302f62616467652e737667)](https://scan.coverity.com/projects/nlohmann-json) 



### code quality 分析、自动化code review

> NOTE: 
>
> 1、我们有sonar，但是只使用了一个

[![Codacy Badge](https://camo.githubusercontent.com/33d1c7f925f04aefd285079d59aee79eaa96790c83a7c6572f1654b0dfa93911/68747470733a2f2f6170692e636f646163792e636f6d2f70726f6a6563742f62616467652f47726164652f6633373332623333323765333433353861306539643166653966363631663038)](https://www.codacy.com/app/nlohmann/json?utm_source=github.com&utm_medium=referral&utm_content=nlohmann/json&utm_campaign=Badge_Grade) 

https://www.codacy.com/product



[![Language grade: C/C++](https://camo.githubusercontent.com/e12dff3b5cf5dcaf0d50f1f822577ac3d24e0c51f77dc55580398c200d368e48/68747470733a2f2f696d672e736869656c64732e696f2f6c67746d2f67726164652f6370702f672f6e6c6f686d616e6e2f6a736f6e2e7376673f6c6f676f3d6c67746d266c6f676f57696474683d3138)](https://lgtm.com/projects/g/nlohmann/json/context:cpp) 

https://lgtm.com/



[![Fuzzing Status](https://camo.githubusercontent.com/a94a3d7894558954f3e601e54b0a1b4834271171aaef56eeed33edde87e7372f/68747470733a2f2f6f73732d66757a7a2d6275696c642d6c6f67732e73746f726167652e676f6f676c65617069732e636f6d2f6261646765732f6a736f6e2e737667)](https://bugs.chromium.org/p/oss-fuzz/issues/list?sort=-opened&can=1&q=proj:json) 

https://bugs.chromium.org/p/oss-fuzz/issues/list



### 在线使用

[![Try online](https://camo.githubusercontent.com/ab84c63f351c1690a61792f19402aa97e95e83456a19fab276730b227008795e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f7472792d6f6e6c696e652d626c75652e737667)](https://wandbox.org/permlink/3lCHrFUZANONKv7a) 



### 文档

[![Documentation](https://camo.githubusercontent.com/baa66788db0de398c9b2722c3d7063864d0f32fb76a004c4149f1da7f0c48939/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646f63732d646f787967656e2d626c75652e737667)](https://nlohmann.github.io/json/doxygen/index.html) 



### CII best practice

[![CII Best Practices](https://camo.githubusercontent.com/a406d9f3d8f22a5de0a433b3e0a6b208ace758d570b0a6901eaafa69c02243cb/68747470733a2f2f626573747072616374696365732e636f7265696e6672617374727563747572652e6f72672f70726f6a656374732f3238392f6261646765)](https://bestpractices.coreinfrastructure.org/projects/289) 



### Serious testing. 

Our class is heavily [unit-tested](https://github.com/nlohmann/json/tree/develop/test/src) and covers [100%](https://coveralls.io/r/nlohmann/json) of the code, including all exceptional behavior. Furthermore, we checked with [Valgrind](https://valgrind.org/) and the [Clang Sanitizers](https://clang.llvm.org/docs/index.html) that there are no memory leaks. [Google OSS-Fuzz](https://github.com/google/oss-fuzz/tree/master/projects/json) additionally runs fuzz tests against all parsers 24/7, effectively executing billions of tests so far. To maintain high quality, the project is following the [Core Infrastructure Initiative (CII) best practices](https://bestpractices.coreinfrastructure.org/projects/289).

> NOTE: 
>
> 1、它的做法是非常值得借鉴的





## [CII Best Practices Badge Program](https://bestpractices.coreinfrastructure.org/en)

The [Linux Foundation (LF)](https://www.linuxfoundation.org/) [Core Infrastructure Initiative (CII)](https://www.coreinfrastructure.org/) Best Practices badge is a way for Free/Libre and Open Source Software (FLOSS) projects to show that they follow best practices. 

### [FLOSS Best Practices Criteria (Passing Badge)](https://bestpractices.coreinfrastructure.org/en/criteria/0)



## Code coverage

### What is code coverage



zhihu [什么是代码覆盖率？](https://www.zhihu.com/question/22244568)

> 是软件测试中的一种度量，描述程序中源代码被测试的比例和程度，所得比例称为**代码覆盖率**。在做**单元测试**时，代码覆盖率常常被拿来作为衡量测试好坏的指标，甚至，用代码覆盖率来考核测试任务完成情况，比如，代码覆盖率必须达到80％或 90％。





zhihu [实际软件工程中是否真的需要100%代码覆盖率（code coverage）？](https://www.zhihu.com/question/29528349) # [ThoughtWorks中国](https://www.zhihu.com/question/29528349/answer/236076742) 

> 代码覆盖率高不能说明代码质量高，但是反过来看，代码覆盖率低，代码质量绝对不会高到哪里去，可以作为测试自我审视的重要工具之一。



**语句覆盖、判定覆盖、条件覆盖、条件判定组合覆盖、多条件覆盖和路径覆盖**

> NOTE: 
>
> 1、需要介绍上述各种指标



### Code coverage的意义

> NOTE: 
>
> 1、做code coverage的意义

### 如何生成代码覆盖率？

1、rdc.hundsun [如何用Gcov优雅地实现代码覆盖率可视化报告?](https://rdc.hundsun.com/portal/article/704.html)

2、csdn [Linux下c/c++项目代码覆盖率的产生方法](https://blog.csdn.net/zm_21/article/details/37820257)

3、csdn [温故而知新：gtest单元测试工具和lcov覆盖率统计工具的结合使用](https://blog.csdn.net/u010312436/article/details/53940309)



## wikipedia [Test-driven Development](http://en.wikipedia.org/wiki/Test-driven_development)

Test-driven development (TDD) is a software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases. This is opposed to software being developed first and test cases created later.



## 测试方案

1、尽可能地实现所有的测试用例全自动化地执行，生成报告（通过率、覆盖率）

2、开发需要自己递交测试用例、测试程序

3、严格的warning、使用多种static code analysis tool

4、自动部署环境

### 现存问题

1、Sonar 

2、缺乏dynamic analysis

### 单元测试

测试类、测试函数

测试用例编写（除了基本的功能测试，还需要测试 极端值、异常）

#### 案例: 

microsoft [Use the C++ Core Guidelines checkers](https://docs.microsoft.com/en-us/cpp/code-quality/using-the-cpp-core-guidelines-checkers?view=msvc-160)



TODO

1、测试程序 和 源程序 如何放



### 接口测试





## Tools



### static code analysis

[Clang-Tidy](https://clang.llvm.org/extra/clang-tidy/#id1)[¶](https://clang.llvm.org/extra/clang-tidy/#clang-tidy)

[Clang Static Analyzer](https://clang.llvm.org/docs/ClangStaticAnalyzer.html)

Clang Thread Safety Analysis[¶](https://clang.llvm.org/docs/ThreadSafetyAnalysis.html#thread-safety-analysis)

### dynamic code analysis

 [Valgrind](https://valgrind.org/) 

[Clang Sanitizers](https://clang.llvm.org/docs/index.html) :

1、MemorySanitizer[¶](https://clang.llvm.org/docs/MemorySanitizer.html#memorysanitizer)

2、UndefinedBehaviorSanitizer[¶](https://clang.llvm.org/docs/UndefinedBehaviorSanitizer.html#undefinedbehaviorsanitizer)

3、LeakSanitizer[¶](https://clang.llvm.org/docs/LeakSanitizer.html#leaksanitizer)