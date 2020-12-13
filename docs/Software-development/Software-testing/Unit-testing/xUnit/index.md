# xUnit

很多unit testing framework都是基于这个framework。

## wikipedia [xUnit](https://en.wikipedia.org/wiki/XUnit)



### xUnit architecture

> NOTE: architecture这对于我们掌握unit testing framework非常重要；xUnit的architecture是非常经典的。
>
> 它是典型的multiple-task model的。

All xUnit frameworks share the following basic component architecture, with some varied implementation details.[[1\]](https://en.wikipedia.org/wiki/XUnit#cite_note-1)

#### Test runner

A [test runner](https://en.wikipedia.org/w/index.php?title=Test_runner&action=edit&redlink=1) is an executable program that runs tests implemented using an **xUnit** framework and reports the test results.[[2\]](https://en.wikipedia.org/wiki/XUnit#cite_note-2)

#### Test case

A [test case](https://en.wikipedia.org/wiki/Test_case) is the most elemental class. All unit tests are inherited from here.

#### Test fixtures

> NOTE: "fixture"在此的含义是"装配"，在下面使用的是context是，显然context的含义是更加准确的。
>
> 为什么"return to the original state after the tests"？
>
> 因为要执行多个test，"return to the original state"能够保证后续的test能够继续执行。
>
> 在后面的"test execution"章节将对它有更好的描述。

A [test fixture](https://en.wikipedia.org/wiki/Test_fixture) (also known as a test context) is the set of [preconditions](https://en.wikipedia.org/wiki/Precondition) or state needed to run a test. The developer should set up a known good state before the tests, and return to the original state after the tests.

#### Test suites

A [test suite](https://en.wikipedia.org/wiki/Test_suite) is a set of tests that all share the same fixture. The order of the tests shouldn't matter.

#### Test execution

The execution of an individual unit test proceeds as follows:

```C++
setup(); /* First, we should prepare our 'world' to make an isolated environment for testing */
...
/* Body of test - Here we make all the tests */
...
teardown(); /* At the end, whether we succeed or fail, we should clean up our 'world' to 
not disturb other tests or code */
```

The `setup()` and `teardown()` methods serve to initialize and clean up **test fixtures**.

> NOTE:
>
> `setup()`
>
> `teardown()`

#### Test result formatter

A [test runner](https://en.wikipedia.org/w/index.php?title=Test_runner&action=edit&redlink=1) produces results in one or more output formats. In addition to a plain, human-readable format, there is often a test result formatter that produces [XML](https://en.wikipedia.org/wiki/XML) output.

#### Assertions

An [assertion](https://en.wikipedia.org/wiki/Assertion_(computing)) is a function or macro that verifies the behavior (or the state) of the unit under test. Usually an assertion expresses a [logical condition](https://en.wikipedia.org/wiki/Logical_conditional) that is true for results expected in a correctly running [system under test](https://en.wikipedia.org/wiki/System_under_test) (SUT). Failure of an assertion typically throws an [exception](https://en.wikipedia.org/wiki/Exception_handling), aborting the execution of the current test.