
题图
http://www.mn.uio.no/ifi/english/about/ole-johan-dahl/media-gallery/photos/13.nygaard-dahl-alltid-foran.jpg


Hello World. 大家好, 我是 pshu. 今天是码农英语课堂的第12期了.


上一期在讲 OO 发明历史的时候留了一个铺垫, 简单的提了下在 OO 诞生的过程中,一篇论文推向了高潮.那是哪篇论文呢?谁写的呢?

首先这篇文章是标题是 "record handling"，下载链接是 https://dl.acm.org/citation.cfm?id=1061041&dl=ACM&coll=DL . 我知道列了你们也不会去看，其实学术圈的也没多少人在看。这篇对 OO 影响很大的论文目前只被引用了13次，累积下载才200+。其实计算机历史上有很多文章是程序员自我提高的很好的阅读材料，看这些比看知乎上网红程序员吵架段位和腔调不知道高到哪里去了。

好了再说作者是谁？Tony Hoare. 估计很多人没听过这个名字, 但是只要你是程序员肯定接触过这位大神的发明之一: qsort 快速排序. Tony 的发明中除了快速排序、快速选择外还有大名鼎鼎的 Hoare Logic 霍尔逻辑，这东西想通过一套符号来描述程序的行为，然后来证明程序的准确性；往学术方向点说就是“形式证明”。现在在一些分享上还会听到，有些语言有完备的形式证明，可以大大减少 bug 的发生。而这霍尔逻辑也是开辟了形式语言的先河。

https://images.theconversation.com/files/63570/original/jcbyhhbs-1415035184.jpg?ixlib=rb-1.1.0&q=45&auto=format&w=754&fit=clip

就这样的以为牛逼的计算机科学家，在2009年伦敦 Qcon 的一个小组讨论中，诚恳的承认自己在计算机领域的一个严重错误：空指针。 下面这段文字是 Tony 的忏悔词。其大意就是在设计语言引用的机制时候，没有抵御住图方便的想法；设计出了空指针。 由于空指针的出现导致了计算机领域的各种 bug ，缺陷和系统崩溃。估计空指针带来了上十亿美元的损失和痛苦。


>I call it my billion-dollar mistake. It was the invention of the null reference in 1965. At that time, I was designing the first comprehensive type system for references in an object oriented language (ALGOL W). My goal was to ensure that all use of references should be absolutely safe, with checking performed automatically by the compiler. But I couldn't resist the temptation to put in a null reference, simply because it was so easy to implement. This has led to innumerable errors, vulnerabilities, and system crashes, which have probably caused a billion dollars of pain and damage in the last forty years.


https://www.infoq.com/presentations/Null-References-The-Billion-Dollar-Mistake-Tony-Hoare

一个如此牛人的自己承认犯了如此严重的错误，那又如何。丝毫不影响 tony 作为一位图灵奖获得者在2011年又获得约翰·冯诺依曼奖。当巨人低头时，侏儒并不会因此而长高。

当然，Tony 是非常真诚的在反思自己的设计，也有不那么真诚的。比如 C 语言的祖师爷 Dennis Ritchie。他说: "C诡异离奇、缺陷重重，却获得巨大成功" (C is quirky, flawed, and an enormous success )。再俏皮点说，“对对对我就是菜，但是随便就5杀对面。” 其实大家可能只看到了 Dennis 这句名言的前半部分，其实这句话后面也有还有一段说明：C 语言本身确实很有用，它同时满足了作为操作系统语言的效率用来取代汇编语言，而且提供了高效的抽象能力，让 C 语言能方便的实现各类算法，同时还有很强的移植性。

>C is quirky, flawed, and an enormous success. While accidents of history surely helped, it evidently satisfied a need for a system implementation language efficient enough to displace assembly language, yet sufficiently abstract and fluent to describe algorithms and interactions in a wide variety of environments.

http://www.azquotes.com/picture-quotes/quote-c-is-quirky-flawed-and-an-enormous-success-dennis-ritchie-59-63-06.jpg


计算机领域的承认自己错误的大牛，

贩卖焦虑
