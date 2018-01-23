hello world, 我是 pshu , 这里是码农英语课堂的第三期.
上一次说 F words, 没有过瘾漏.今天在讲几个 F word.

# flaky ***['fleiki]***

Twitter 有个非常有名的生成序列的算法  *snowflake*, 它们是来自用一个词根.(如果对 snowflake 感兴趣的话可以,可以看这里)
这里 flake ***[flek]*** 是小薄片的意思. snowflake 就是雪花片的意思.

但是 flaky 是不可靠的意思, 程序员能接触的话就是  `flaky test`. 在 node.js 项目的 wiki 里面就有一个简短的关于
flaky test的介绍.

> Flaky tests are tests that fail intermittently. This can happen if there is an underlying bug that only happens intermittently. Or it could also happen if a test is timing-dependent and affected by environmental conditions such as the speed of the machine running the test.

* intermittently [intə'mitəntli] 间歇性的.

讲到 intermittently 这个单词,可以扩展说下就是外国的网友如果抱怨网络很差的时候会用
intermittentnet 这个复合词; 间歇性的网络,就是时有时无的网络,就是我们所谓的"卡".
而且这个复合词和互联网 internet 非常的接近,可以一起记忆.

说回到 flaky, 它除了可以用来形容此测试用力不稳定外,还可以形容人, 比如 flaky man.
Flaky man 不是稳定的人的意思, 是说这个人说话不算数, 不靠谱;  flake 这个单词也直接可以表达这个意思.

Flaky test 有时候确实让人听恼火的, 让程序员更加心惊肉跳的就是 "fatal exception". 下面我们来说说 ***fatal*** 这个单词.

# fatal ***[ˈfetl]***

![fatal exception]()

fatal源自词根 fate(宿命), 想对于 destiny(命运), 宿命是无法改变的.
所谓的"阎王叫人三更死，谁敢留人到五更", 操作系统要了进程(process)命,没有方法再活下来的.
唯一的方法就是在启动一个新的进程来替代原来的进程工作. 把退出的进程重新启动起来的进程我们一般叫 daemon ['dimən] 守护进程.
用来保护你的服务不会因为程序的 fatal excepion 而退出.

现在 pshu 现在开发的一些服务都不在单独的去写一个守护进程了, 而是通过进程管理(process mananger)程序来让服务一直在线. 在 node.js 技术圈中,最有名的自然是 `pm2` 了.  进程管理程序除了让进程在退后能够重新被拉起来,还有很多其他额外的功能. 以pm2为例: 它支持配置当进程消耗的内存消耗超过一定量的时候(`max-memory-restart选项`),就重启进程,这个配置在内存泄漏还没有查出来之前,可以作为一个临时方案;比如还有通过命令 `scale service_name number_sacle_to`,将对应的服务进程的数目增加或者减少. 

将服务的开发和服务如何运行分离开来考虑,在开发是专注逻辑; 在部署时候通过专业进程管理来管理服务.这也是对自己开发的流程的 `do one thing`.


最后送给大家一个单词, focus

a focus quote needed.
