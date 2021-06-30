# Software testing

test是软件开发过程中非常重要的一环。

## wikipedia [Software testing](https://en.wikipedia.org/wiki/Software_testing)



## Successful case

应用test的非常成功的案例。

### [SQLite](https://sqlite.org/about.html)

> SQLite is [very carefully tested](https://sqlite.org/testing.html) prior to every release and has a reputation for being very reliable. Most of the SQLite source code is devoted purely to testing and verification. An automated test suite runs millions and millions of test cases involving hundreds of millions of individual SQL statements and achieves [100% branch test coverage](https://sqlite.org/testing.html#coverage). SQLite responds gracefully to memory allocation failures and disk I/O errors. Transactions are [ACID](http://en.wikipedia.org/wiki/ACID) even if interrupted by system crashes or power failures. All of this is verified by the automated tests using special test harnesses which simulate system failures. 

测试的**全面性**:

- 可能的场景
- 代码层: coverage

在[How SQLite Is Tested](https://sqlite.org/testing.html)描述了sqlite的测试方法。

### [nlohmann](https://github.com/nlohmann)/**[json](https://github.com/nlohmann/json)**

Our class is heavily [unit-tested](https://github.com/nlohmann/json/tree/develop/test/src) and covers [100%](https://coveralls.io/r/nlohmann/json) of the code, including all exceptional behavior. Furthermore, we checked with [Valgrind](https://valgrind.org/) and the [Clang Sanitizers](https://clang.llvm.org/docs/index.html) that there are no memory leaks. [Google OSS-Fuzz](https://github.com/google/oss-fuzz/tree/master/projects/json) additionally runs fuzz tests against all parsers 24/7, effectively executing billions of tests so far. To maintain high quality, the project is following the [Core Infrastructure Initiative (CII) best practices](https://bestpractices.coreinfrastructure.org/projects/289).



## wikipedia [List of unit testing frameworks](https://en.wikipedia.org/wiki/List_of_unit_testing_frameworks#C++)

