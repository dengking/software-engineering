# Heisenbug

一、51cto [计算机程序中 Bug 的类型大全与历史](https://mobile.51cto.com/comment-455507.htm)

> 所有有阅历的程序员都遇到过这种情况：有个bug让程序崩溃了，但当程序重启后，这个bug消失了。不论你用多少的时间和精力来试图让bug重现，bug就是人间蒸发了。这样的bug被称为海森堡bug(Heisenbug)，它是用德国物理学家、量子力学的创始人、“哥本哈根学派”代表性人物维尔纳·海森堡(Werner Heisenber)的名字命名，隐射其著名的“[测不准原理](http://zh.wikipedia.org/wiki/測不準原理)”（又称“海森堡不确定性原理”）。根据他的这个理论，在某一个给定的时间点，一个电子所处的位置是无法确定的，也无法跟踪它的轨迹。当你去debug、探测、隔离一个bug时，你的这些动作会导致bug改变它们的行为表现，这些bug就叫做海森堡bug(Heisenbugs)。这种事情是有可能的，比如，如果你使用未初始化的变量，这会导致一个bug出现。然而，当你试图debug这个程序时，程序却没有任何异常，因为很多的debug工具会自动初始化变量为0，所以这些bug将不会再现。

二、race condition是典型的Heisenbug



## baike [海森堡bug](https://baike.baidu.com/item/%E6%B5%B7%E6%A3%AE%E5%A0%A1bug/22703474?fr=aladdin)



## wikipedia [Heisenbug](https://en.wikipedia.org/wiki/Heisenbug)



## sourceware [The Heisenberg Debugging Technology](https://sourceware.org/gdb/talks/esc-west-1999/)
