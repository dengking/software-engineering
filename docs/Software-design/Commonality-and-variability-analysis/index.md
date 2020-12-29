# Commonality-variability analysis

"commonality variability analysis"是我在阅读wikipedia [*Modern C++ Design* # Policy-based design](https://en.wikipedia.org/wiki/Modern_C%2B%2B_Design#Policy-based_design)时，发现的:

> The main idea is to use **commonality-variability analysis** to divide the type into the **fixed implementation** and interface, the policy-based class, and the different policies. The trick is to know what goes into the main class, and what policies should one create. 



## Implementation

"Commonality-variability analysis"告诉了我们分析方法，在进行实现的时候，我们可以采取: 

### Program to an abstraction and polymorphism

commonality 公共，对应的是code reuse；

variability  可变，差异，对应的是abstraction 和 polymorphism；



## TODO

informit [Commonality/Variability and Abstract Classes](https://www.informit.com/articles/article.aspx?p=167890&seqNum=5)

https://www.oreilly.com/library/view/essential-skills-for/9780321700469/ch10.html

https://www.oreilly.com/library/view/design-patterns-explained/0201715945/0201715945_ch21lev1sec4.html

https://www.dre.vanderbilt.edu/~schmidt/PDF/Commonality_Variability.pdf

https://portal.netobjectives.com/wp-content/uploads/2018/01/Introduction_CommonalityVariabilityAnalysis.pdf

https://portal.netobjectives.com/pages/learning/webinars-and-podcasts/commonality-variability-analysis/