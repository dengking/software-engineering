# Package manager

do not [Reinventing the wheel](https://en.wikipedia.org/wiki/Reinventing_the_wheel)是软件工程领域的最佳实践，所以各种编程语言提供了丰富的library，往往一个工程需要依赖各种各样的library；

在Java的世界中，常用的依赖管理工具是[maven](http://maven.apache.org/)，依赖是伴随工程文件的，而非伴随Java解释器；在`pom.xml`中声明这个项目所需的依赖；

在python的世界中，常用的依赖管理工具是[pip](https://pip.pypa.io/en/stable/)，依赖不是伴随工程文件的，而伴随python解释器；由于依赖是伴随python解释器的，所以为了保持各个项目的独立，在python中有各种环境管理工具，如`virtualenv`，`conda`等等；

