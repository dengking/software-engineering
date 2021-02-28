# wikipedia [Software build](https://en.wikipedia.org/wiki/Software_build)

In the field of [software development](https://en.wikipedia.org/wiki/Software_development), build has often referred either to the process of converting [source code](https://en.wikipedia.org/wiki/Source_code) files into standalone [software artifact(s)](https://en.wikipedia.org/wiki/Artifact_(software_development)) that can be run on a computer, or the result of doing so. 

## Functions

Building software is an end-to-end process that involves many distinct functions. Some of these functions are described below.

### Version control

The [version control](https://en.wikipedia.org/wiki/Version_control) function carries out activities such as workspace creation and updating, baselining and reporting. It creates an environment for the build process to run in and captures metadata about the inputs and outputs of the build process to ensure repeatability and reliability.

Tools such as [Git](https://en.wikipedia.org/wiki/Git_(software)), [AccuRev](https://en.wikipedia.org/wiki/AccuRev_SCM) or [StarTeam](https://en.wikipedia.org/wiki/StarTeam) help with these tasks by offering tools to tag specific points in history as being important, and more.

### Code quality

Also known as [static program analysis/static code analysis](https://en.wikipedia.org/wiki/Static_program_analysis) this function is responsible for checking developers have adhered to the seven axes of code quality: comments, unit tests, duplication, complexity, coding rules, potential bugs and architecture & design.

Ensuring a project has high-quality code results in fewer bugs and influences nonfunctional requirements such as maintainability, extensibility and readability, which have a direct impact on the [ROI](https://en.wikipedia.org/wiki/Return_on_investment) for a business.

### Compilation

This is only a small feature of managing the build process. The compilation function turns source files into directly executable or intermediate objects. Not every project will require this function.

While for simple programs the process consists of a single file being [compiled](https://en.wikipedia.org/wiki/Compiled), for complex software the source code may consist of many files and may be combined in different ways to produce many different versions.

## Build tools

The process of building a [computer program](https://en.wikipedia.org/wiki/Computer_program) is usually managed by a [build tool](https://en.wikipedia.org/wiki/Build_tool), a program that coordinates and controls other programs. Examples of such a program are [make](https://en.wikipedia.org/wiki/Make_(software)), [Gradle](https://en.wikipedia.org/wiki/Gradle), Meister by [OpenMake Software](https://en.wikipedia.org/wiki/OpenMake_Software), [Ant](https://en.wikipedia.org/wiki/Ant_(software)), [Maven](https://en.wikipedia.org/wiki/Maven_(software)), [Rake](https://en.wikipedia.org/wiki/Rake_(software)), [SCons](https://en.wikipedia.org/wiki/SCons) and [Phing](http://www.phing.info/). The build utility typically needs to [compile](https://en.wikipedia.org/wiki/Compiler) the various files, in the correct order. If the source code in a particular file has not changed then it may not need to be [recompiled](https://en.wikipedia.org/wiki/Recompile) (may not rather than need not because it may itself depend on other files that have changed). Sophisticated build utilities and linkers attempt to refrain from recompiling code that does not need it, to shorten the time required to complete the build. A more complex process may involve other programs producing code or data as part of the build process.



# [Build automation](https://en.wikipedia.org/wiki/Build_automation)