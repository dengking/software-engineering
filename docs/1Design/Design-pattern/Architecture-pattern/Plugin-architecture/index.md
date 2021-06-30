# Plugin architecture

plugin的含义是什么？参见wikipedia [Plug-in (computing)](https://en.wikipedia.org/wiki/Plug-in_(computing))，显然，基于plugin的architecture就是本文需要阐述的plugin  architecture。plugin是一种概念，它可以以多种方式来进行实现，比如shared library，Library-base architecture其实也可以看做是一种plugin architecture。

> NOTE: library-based architecture是我在阅读clang的doc时候，其中提出的一个概念。

在阅读[Clang - Features and Goals](http://clang.llvm.org/features.html#libraryarch)时，其Library Based Architecture令我印象深刻，据我所知的，还有采用这种架构的有

| software                                                     | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [nginx](https://nginx.org/en/docs/)                          | [nginx](https://nginx.org/en/docs/)提供了非常多的Modules，这些Modules就是一个一个的library |
| [redis](https://redis.io/modules)                            | [Redis Modules](https://redis.io/modules)，这些Modules就是一个一个的library |
| [Tuxedo (software)](https://en.wikipedia.org/wiki/Tuxedo_(software)) |                                                              |
| [cpython](https://www.python.org/)                           | [cpython](https://www.python.org/)也可以看做是library-base architecture，因为它允许Extending and Embedding the Python Interpreter[¶](https://docs.python.org/3/extending/index.html#extending-and-embedding-the-python-interpreter) 参见：<br>- [python bindings, how does it work?](https://stackoverflow.com/questions/10202306/python-bindings-how-does-it-work) <br>- [dlopen](http://man7.org/linux/man-pages/man3/dlopen.3.html) |
| operating system kernel                                      | 大多数现代操作系统都支持[loadable kernel module](https://en.wikipedia.org/wiki/Loadable_kernel_module)特性 |
| SQLite                                                       | 参见:<br>- [The Virtual Table Mechanism Of SQLite](https://sqlite.org/vtab.html)<br>- [Run-Time Loadable Extensions](https://sqlite.org/loadext.html) |





## Reading list 

### [Building Your Own Plugin Framework](https://www.drdobbs.com/cpp/building-your-own-plugin-framework-part/204202899?pgno=1)





## 实现

### [dlopen(3)](https://linux.die.net/man/3/dlopen)



### [uselib(2)](https://linux.die.net/man/2/uselib) 

### [Building a Simple C++ Cross-platform Plugin System](https://sourcey.com/articles/building-a-simple-cpp-cross-platform-plugin-system)



### [Build a Pluggable Application with IoC Container](https://www.codeproject.com/Articles/361695/Build-a-Pluggable-Application-with-IoC-Container)



### [ffead-cpp](https://github.com/sumeetchhetri/ffead-cpp)



### [Making a Plugin System](http://www.cplusplus.com/articles/48TbqMoL/)



### [Introducing the new C++ plugins](https://blog.gradle.org/introducing-the-new-cpp-plugins)



### [Pluga](https://sourcey.com/pluga)



### [Implementing A Plugin System in C or C++ [closed]](https://stackoverflow.com/questions/708527/implementing-a-plugin-system-in-c-or-c)



### [Dynamic Loading of Modules](https://developer.gnome.org/glib/stable/glib-Dynamic-Loading-of-Modules.html)



### [dlvhex](http://www.kr.tuwien.ac.at/research/systems/dlvhex/doc2x/index.html) 



### [Chapter 12. Boost.DLL](https://www.boost.org/doc/libs/1_65_1/doc/html/boost_dll.html)

## Middleware

https://en.wikipedia.org/wiki/Middleware

### Message-oriented middleware

https://en.wikipedia.org/wiki/Message-oriented_middleware






