

Hello World. 大家好, 我是 pshu. 今天是码农英语课堂的第11期了.


这期和大家聊一下 Object Orientation 发明的历史，因为这段历史有较多的细节和本节目的特色所以会分成两期来讲。希望大家喜欢。


# 双星的陨落

2002年对于 OO 领域或者说计算机领域来说的话是非常压抑的一年. 因为 OO 领域两个领袖人物 Ole-Johan Dahl (简写为 OJD，O里行道), Kristen Nygaard  （简写 KN， 库里斯提 泥~good）相继去世. （两位前辈名字的准确读法参考：https://youtu.be/B1Hvxxv2AEY?t=191 ）

先是 OJD 去世 , KN 还给他写了讣告. 几个月后 KN 也因为心脏病突发去世. 两个位巨星的陨落是给计算机领域的巨大的损失. 当年很多的计算机期刊杂志都发文来缅怀两位巨星.

那在现在各个语言都在鼓吹 functional programing (函数式编程)的时候, pshu 就反其道而行来讲一讲面向对象编程诞生的历史.

为了尽量真实重现当年 OO 发明的历史，本文参考了论文 "the birth of simula" 的第二部分 "a chronological overview" 和 OJD 在去世一年写的论文 "the birth of OO".

在开始讲历史之间,码农英语课堂先讲个单词。就是刚才提到的 chronological 的词根：chrono

chrono: 时间顺序的, 这次是源自希腊语(Greek)时间的单词 khronos
我们平时最长碰到的就是  synchronize 同步. syn 是表示一起的意思，syndrome 并发症。


## 早期设计阶段 The early design phase (1961 - 1962/8月)

KN 在挪威计算级中心(Norwegian Computing Center, NCC)负责一些运筹学方便的研究, 研究的时候会需要通过模拟的方式判断系统的优劣, 但是原先系统模拟的方法 KN 并不满意. KN认为非常需要一种更加高抽象层面的表示方法来描述他研究的系统, KN 在和以为朋友写信谈到这个事情的时候就说, 我的想法是已经有了雏形了,就是想找一个编程高手帮忙实现, 而且人选已经有了.

这里不是"就差一个程序员"的故事, KN 差的是一个比我还厉害的程序员. 因为 KN 在开始这个项目之前已经是挪威计算级中心(NCC) 的研究主任(director of research). 如果你说他不会写代码那真是太小看老一辈的 Geek 了.

这个人选呢就是 KN 前工作单位"挪威国防研究所"(Norwegian Defence Research Establishment, NDRE)的同事, 也就是故事的另外一位主角 OJD. 他们一起在国防研究所工作的时候是完全两个不同的领域, KN 做过核反应堆和作战系统的研究; 而 OJD 主要是从事高级语言的发明. OJD 在2001的论文里面也说了正是以为他们两个人研究领域的不同才能促成 OO 的诞生, 那个时候就有我们现在常说的跨界合作了.

好了两个大牛要一起干事业就想给事业取个好名字, SIMULA (SIMUlation LAnguage). 在这一年多的时间里面两位大牛设计了 Simula 了一些语言的规范(specification), 并且在一次会议上发表了. 大牛做东西就是不一样,东西还没出来就能发论文了什么.

这个阶段的话的产出就叫做 simula 0; 当初的实现的思路是做一个 Algol 语言的预处理器. 而为什么要选择 Algol 有三条理由,其中两条是和技术相关, 最后一条原因是 "European patriotism" - 爱欧洲主义.

patriotism 爱国主义，这个单词源自词根，patriot； 而 patriot 的词源是希腊语的词根 patr，而这个 patr 是变形次词根 father.

这里为什么要说"爱欧洲"呢? 当时计算机领域是美国独大的一个局面. 那个时期四个被公认的对当代计算机语言影响最大的语言: Lisp, Fortran, COBOL, Algol. 只有 Alogl 是欧洲人(主要是德国)发明的, 其他是美帝国主义的. 所以在合理的选择范围内, 选择国货这个是人之常情哈.



happy patriotisim!


## The Simula 1 design & implement phase ( 1962 秋 - 1964 三月 - 1965 一月)

KN 忙于非科研工作 (organizational and financial matters), 但是学术牛人不完全是书呆子, 他给 NCC 谈下了打折买了一台大型计算机(UNIVAC 1107) 和项目的资金.

http://hopl.info/showhardware.prx?id=28

各司其职.
OJD 原先基于预处理的方式来设计一个新语言对他们的项目还是不太现实. 当时他们用一个模拟 station(站点)来处理 customer(客户)的一个例子来 dogfooding 这个新语言的; 也有说法是模拟调度船只在海峡之间调度的例子,其实本质都差不多. 那完全基于 Algol的过程式语言来描述调度系统中的 "station"(主动处理部分) 和 customer(完全被动被处理的数据) 也有非常大的限制.

然而重要的历史时刻就到来了, OJD 突发奇想:
如果把对 station 和 customer 的描述从栈上移出来, 放到一个我们现在称为堆的地方,一切都变得非常的方便. 而且模拟的系统中的实体可以统一成一个概念, 不会像 simula 0中模拟的对象有主动的被动的区分.

就这样语言设计层面引入了一个叫 "process" 的概念, 这个 process 和 pshu 之前的创刊号中的 process 不是一个意思. Simula 的 process 相当于我们现在所说的 object 的概念的雏形.

有了这个想法时候,OJD 就开始紧锣密鼓的实现. 这次实现就是不会实现一个 Algol 语言的预处理器, 而是完全一个新的编译器. 大概用了五个月的时间就实现了历史上第一个有面向对象思想的语言 Simula 1. 之所以能这么快的作出一个全新的编辑器, 也得益于 NCC 的其他同事和 UNIAC 1107 这个计算机厂商的 Algol 编辑器专家的支持.

## Simula 67 的诞生

实现了 Simula 1 之后 KN 和 OJD 就在各种工作中使用, 那使用然后是肯定是爽爽爽啊! 于是他们觉得 Simulua 1 的思想如果应用到日常的编程中也肯定是如虎添翼. 所以他们就开始着手发明一个新的语言能够在通用的场景下使用. 这个想法最终被一个叫 CAR hoare 人的论文点燃爆点, 这篇文章题目提出了 class 和 subclass 的概念, 而且还提议了用"点符号"(dot) 来访问对象的程序员. 这个就和我现代使用的面向对象的语法非常的类似了. 关于新的面向对象语言的规范的讨论越来越多,于是将新的语言命名为 Simula 67. 因为划时代的年份就是1967年.为了推动 Simula 67发展还是成立了一个叫 SSG 的委员会来讨论语言规范和实现.

至此 Simula 67 基本算是诞生了, 也就是说 object orientation 也正式发明了. 也有一些说法是 1966年就是 OO 诞生的元年. pshu 个人认为的 OO 元年是1964年, 就是 ODJ 那个灵光一现的 aha moment (顿悟时刻), 想到把数据结构挪到堆上的瞬间. 当然咯, 每个人都有各自的看法.








