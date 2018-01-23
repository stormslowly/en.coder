

```
#define true false
```

hello world

大家好, 我是 pshu . 今天是码农英语课堂的第二期. 今天和大家一起聊下编程工作中常碰见
的就两个 F 开头的单词. 可能大家最常用那个 "the F word".
不过今天 pshu 介绍的是编程工作中经常碰到的 "F word".

# false

![boolean](https://qph.ec.quoracdn.net/main-qimg-805e34db3accae95da9e1bebb6564135)

程序员每天面对的都是逻辑问题,自然布尔逻辑中的两个基本的定义 真(true) 和 假(false)
必然每天要用到.

那在编程中,当我们使用到布尔变量的时候,一定要记得给它们取一个好名字. 比如 `hasVisited`,
`isValid`, 这样的命名在面向对象的编程范式会有很好的可读性.

```
if(city.hasVisted){
	this.visit(city.neighbor)
}
```

针对布尔类型,有一点非常重要的就是:

> Never ever use boolean as function parameters

> 永远不要用布尔类型作为函数参数来使用.

相信很多人都知道"一个函数只做一件事情"(Do one thing) 的说法. 那如果你的函数用布尔类型
作为函数参数的话,函数内部肯定会因为布尔参数的真假做不同的事情, 显然就不是 "Do one thing"了

还有如果一个函数采用布尔类型作为参数的话,它的可读性非常的差.
`redraw(false)` 那这次重绘是重绘了呢,还是没有重绘呢? 显然给读代码的人带来了疑惑.
虽然这个问题可以通过一些方式来解决, 但本质上来说是用布尔类型作为函数参数带来的额外工作量.

# failure

![TDD](http://www.agilenutshell.com/assets/test-driven-development/tdd-circle-of-life.png)

作为一个崇尚 TDD(test driven development) 的开发者, 我每天就是要处理各种失败测试用例(failing tests).

巴顿将军(General George Patton)说过:

> A pint of sweat, saves a gallon of blood.

pint(品脱:0.473升) 和 gallon(加仑:3.785升)都是体积的计量单位.
那这里的 save 的一次是节省的意思, 直译过来就是多流一品脱的汗,能让你在战场上省下一加仑的血.
意译过来就是我们常说的,"平时多流汗,战时少流血".
如果我在开发过程中多尝试些测试用例,上线了问题自然就少了.

最后再引用民间航天领域的开拓者 Burt Rutan 的一句话

![Burt Rutan](https://image-store.slidesharecdn.com/022c71fb-5a2d-4a93-9812-522ce0c3b278-large.png)

> Testing leads to failure, and failure leads to understanding.
> 测试会暴露出失败, 但失败会带来更深的理解.

给大家撒一波鸡汤, 开发中勇于挑战代码的失败, 挑战的次数多了自然也会进步了.

最后再送给大家最后一个单词 fun.
祝大家编程快乐

Have Fun!


8888
