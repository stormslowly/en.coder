
当巨人低头时，侏儒并不会因此而长高。

题图
http://www.mn.uio.no/ifi/english/about/ole-johan-dahl/media-gallery/photos/13.nygaard-dahl-alltid-foran.jpg


Hello World. 大家好, 我是 pshu. 今天是码农英语课堂的第12期了.


上一期在讲 OO 发明历史的时候留了一个铺垫, 简单的提了下在 OO 诞生的过程中,一篇论文推向了高潮.那是哪篇论文呢?谁写的呢?

首先这篇文章是标题是 "record handling"，下载链接是 https://dl.acm.org/citation.cfm?id=1061041&dl=ACM&coll=DL . 我知道列了你们也不会去看，其实学术圈的也没多少人在看。这篇对 OO 影响很大的论文目前只被引用了13次，累积下载才200+。其实计算机历史上有很多文章是程序员自我提高的很好的阅读材料，看这些比看知乎上网红程序员吵架段位和腔调不知道高到哪里去了。

好了再说作者是谁？Tony Hoare. 估计很多人没听过这个名字, 但是只要你是程序员肯定接触过这位大神的发明之一: qsort 快速排序. Tony 的发明中除了快速排序、快速选择外还有大名鼎鼎的 Hoare Logic 霍尔逻辑，这东西想通过一套符号来描述程序的行为，然后来证明程序的准确性；往学术方向点说就是“形式证明”。现在在一些分享上还会听到，有些语言有完备的形式证明，可以大大减少 bug 的发生。而这霍尔逻辑也是开辟了形式语言的先河。

https://images.theconversation.com/files/63570/original/jcbyhhbs-1415035184.jpg?ixlib=rb-1.1.0&q=45&auto=format&w=754&fit=clip

就这样的一位牛逼的计算机科学家，在2009年伦敦 Qcon 的一个小组讨论中，诚恳的承认自己在计算机领域的一个严重错误：空指针。 下面这段文字是 Tony 的忏悔词。其大意就是在设计语言引用的机制时候，没有抵御住图方便的想法；设计出了空指针。 由于空指针的出现导致了计算机领域的各种 bug ，缺陷和系统崩溃。估计空指针带来了上十亿美元的损失和痛苦。


>I call it my billion-dollar mistake. It was the invention of the null reference in 1965. At that time, I was designing the first comprehensive type system for references in an object oriented language (ALGOL W). My goal was to ensure that all use of references should be absolutely safe, with checking performed automatically by the compiler. But I couldn't resist the temptation to put in a null reference, simply because it was so easy to implement. This has led to innumerable errors, vulnerabilities, and system crashes, which have probably caused a billion dollars of pain and damage in the last forty years.


https://www.infoq.com/presentations/Null-References-The-Billion-Dollar-Mistake-Tony-Hoare

一个如此牛人的自己承认犯了如此严重的错误，那又如何。丝毫不影响 tony 作为一位图灵奖获得者在2011年又获得约翰·冯诺依曼奖。
当然，Tony 是非常真诚的在反思自己的设计，也有不那么真诚的反思。比如 C 语言的祖师爷 Dennis Ritchie。他说: "C诡异离奇、缺陷重重，却获得巨大成功" (C is quirky, flawed, and an enormous success )。再俏皮点说，“对对对我就是菜，但是随便就5杀对面。” 其实大家可能只看到了 Dennis 这句名言的前半部分，其实这句话后面也有还有一段说明：C 语言本身确实很有用，它同时满足了作为操作系统语言在效率上的需要，以此来取代汇编语言，而且提供了高效的抽象能力，让 C 语言能方便的实现各类算法，同时还有很强的可移植性。

>C is quirky, flawed, and an enormous success. While accidents of history surely helped, it evidently satisfied a need for a system implementation language efficient enough to displace assembly language, yet sufficiently abstract and fluent to describe algorithms and interactions in a wide variety of environments.

http://www.azquotes.com/picture-quotes/quote-c-is-quirky-flawed-and-an-enormous-success-dennis-ritchie-59-63-06.jpg



刚才说得是计算机历史上的两次认错，那在当代也出现了一个动静比较大的认错就是 Ryan Dahl 在今年欧洲 JSConf 上的演讲 “10 Things I Regret About Node.js”, 其实在我看来有些错误也并不是那么的致命，不如 Promise 的支持，都可以通过社区自己来解决。Ryan 只是后悔(regret)的当初没有这么做。可是当媒体捕捉到了这个事件之后就出现了类似的标题《Node 之父：Node 失误太多无力回天，Deno 前景明朗》和《Node Bug 太多惨遭创始人抛弃，前端开发要变天？》， 甚至我还看到 Node.js 已死的惊悚标题。

现在这个事件已经过于一个月了，热度也凉了（一来我不是蹭热度的那种人，二来懒癌晚期写稿太慢），pshu 打算说说自己的看法。大牛承认了自己错误，可是那有如何呢？大牛依然是大牛，巨人还是巨人。Nullpointerexception 依然出现在你的日志里面；你还是搞不懂的 C 语言的指针。

再看看 Ryan 的这次演讲，虽然演讲稿的 pdf 早早就放出了，视频大概过了一个月(2018-06-06)才出来。放出来后我第一时间也做了搬运。现在时间过去了一个月了，看看我自己在 QQ 视频的播放数量只有1; 也有人在 B 站搬运了，播放数也只有50+。媒体那些吓死人的标题只是为了博取眼球和贩卖焦虑。node.js 死了会如何？Node.js 真的会死吗？这些问题的我也没有好的答案。但是大家可以参考下 Java。每每有一个新的语言发布了，就会出一批 Java 已死的文章来痛批 Java 这个老顽固。可是十多年了 Java 就没跌出过 TOBIE 前三。

讨论语言的生死真的没有意义。关键要看你用语言创造了什么？精通语言 IDE 安装和各种 HelloWorld不会给你带来半点进步。当那些技术巨人在低头道歉的时候，如果你还在他的脚底，自己的长高的错觉会让你欢呼雀跃；但是你要是站在巨人的肩膀上，他的低头却能给你带来一片新的视野。

https://mmbiz.qpic.cn/mmbiz_png/dlEwIVcKGs7Gq5cKvxCiakFWcDpAUSVic5iaDBS2QvPuD0zgTwnOuscQIqd1XW0GDLrdjk1Pia7sLjFJECRfyVTtrQ/0?wx_fmt=png

最后的最后，还是码农英语课堂里面一直讲的那句话。面对各种信息的时候，希望大家能找到信息和知识原来的样子和面貌；拒绝二手知识。

点击原文地址 https://v.qq.com/x/page/p0680nfnfs3.html
 