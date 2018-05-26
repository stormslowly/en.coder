

Hello World. 大家好, 我是 pshu. 今天是码农英语课堂的第11期了.


今天和大家聊一下 OO 发明的历史.


# 双子星的陨落

2002年对于 OO 领域或者说计算机领域来说的话是非常压抑的一年. 因为 OO 领域两个领袖人物相继去世.

先是 OJD 去世 , KN 还给他写了讣告. 几个月后 KN 也因为心脏病突发去世. 两个位巨星的陨落


参考 THE BIRTH OF SIMULA 第二部分 A CHRONOLOGICAL OVERVIEW

1. 早期设计阶段 The early design phase (1961- 1962 8月)

原先系统模拟的方法并不是让 KN 这么满意, 非常需要一种更加高抽象层面的表示方法来描述他研究的系统. 这里不是"就差一个程序员"了,是差一个比我还厉害的程序员.因为 KN 在开始这个项目之前已经是挪威计算级中心(Norwegian Computing Center, NCC) 的研究主任(director of research). 如果你说他不会写代码那真是太小看老一辈的 Geek 了.

KN 就从前工作单位"挪威国防研究所"(Norwegian Defence Research Establishment, NDRE)撬了一个前同事, 就是故事的另外一位主角 OJD. 那他们一起在国防研究所工作的时候是完全两个不同的领域, KN 做过核反应堆和作战系统的研究; 而 OJD 主要是从事高级语言的发明.

好了两个大牛要一起干事业就想给事业取个好名字, SIMULA (SIMUlation LAnguage)在这一年多的时间里面两位大牛设计了 Simula 了一些语言的规范(specification), 并且在一次会议上发表了. 大牛做东西就是不一样,东西还没出来就能发论文了什么.

这个阶段的话的产出就叫做 simula 0; 当初的实现的思路是做一个 Algol 语言的预处理器. 而为什么要选择 Algol 有三条理由,其中两条是和技术相关, 最后一条原因是 "European patriotism" - 爱洲主义.

patriotism 一般是表示爱国主义. 这里为什么要说"爱洲"呢? 但是计算机领域是美国独大的一个局面. 那个时期四个被公认的对当代计算机语言影响最大的语言: Lisp, Fortran, COBOL, Algol. 只有 Alogl 是欧洲人(主要是德国)发明的, 其他是美帝国主义的. 所以在合理的选择范围内, 选择国货这个是人之常情哈.

2. The Simula 1 design phase ( 1962 秋 - 1964 三月 - 1965 一月)

KN 忙于非科研工作 (organizational and financial matters), 但是学术牛人不完全是书呆子, 他给 NCC 谈下了打折买了一台大型计算机(UNIVAC 1107) 和项目的资金.

http://hopl.info/showhardware.prx?id=28

各司其职.
OJD 原先基于预处理的方式来设计一个新语言对他们的项目还是不太现实.
同时基于栈的过程式语言来描述调度系统中的 "station" 和 customer 也有非常大的限制.

然后重要的历史时刻就到来了, OJD 想:
如果把对 station 和 customer 的描述从栈上移出来, 放到一个我们现在称为堆的地方,一切都变得非常的方便. 而且模拟的系统中的实体可以统一成一个概念, 不会像 simula 0中模拟的对象有主动的被动的区分.

在语言设计层面引入了一个叫 "process" 的概念, 这个 process 和 pshu 之前的创刊号中的 process 不是一个意思. Simula 的 process 相当于我们现在所说的 object 的概念的雏形.




3. Simula 1 的实现.
