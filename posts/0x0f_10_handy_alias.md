10个好用的 shell 别名
----

上一篇推文讲了，程序员要巧干不要蛮干，注重效率提高。今天再分享一篇提升“微效率”的文章。原文标题：《10 handy Bash aliases for Linux》，原文地址 https://opensource.com/article/18/9/handy-bash-aliases 。p叔觉得有几个别名还是挺有用的，除了把这些别名分享给大家。文章用的单词和句子都比较简单，大家可以尝试直接看看原文。

>How many times have you repeatedly typed out a long command on the command line and wished there was a way to save it for later? This is where Bash aliases come in handy. They allow you to ***condense*** long, ***cryptic*** commands down to something easy to remember and use. Need some examples to get you started? No problem!

有些很长的命令敲得多了，是不是很想有个地方保存在这个命令，下次用就能节省很多时间了。Bash 的别名就是用来做这个的，让冗长的命令变得简短 *(原文用了 condense，凝结这个单词用来表示命令缩短了，这里 pshu 意译了下 )*，晦涩难用 (*cryptic原意是神秘的意思；程序员常见的变形是 crypto，加密 cryptograph 的简写，有些命令确实难用的就像加密了一样 )*的变得简单易用。直接给你们上例子。

 原文中还顺便提了下，如果你要修改 bash 别名的话是要编辑  `bash_profile`  这个文件。这些基础的东西 pshu 就带过了。如果不知道的可以去看下原文。

## tar 
来的第一个例子就是要解决 cryptic command。`tar` 命令。
给出的别名 `alias  untar='tar -zxvf '` 这几个命令行选项是什么意思先不说，我们先看一个 xkcd 的漫画(https://xkcd.com/1168/)就知道 tar 是有多少的 cryptic。它是一个不 google 你用不好的命令。

![xkcd  tar](http://cdn2.51ulong.com/18-11-1/42769127.jpg)

不过要想记住还是有方法，下面这个咆哮体就能帮你记住。记住了就不要用这个别名了，下次直接可以在其他同事面前炫技了。：p

![咆哮法记 tar 用法](http://cdn2.51ulong.com/18-11-1/56585117.jpg)

## wget

`wget` pshu用的比较少（其实是没怎么用），为了看下 wget 的手册还安装了下。`alias  wget='wget -c '` 命令可以帮在下载中挂断后恢复下载。这里这个 c 就是***continue***的意思。


pshu常用的下载命令是`curl`, curl 对应的选项是 `-C, --continue-at <offset>` , 是要通过 offset 来指定继续下载的位置。如果要自动获取 offset 的话只要使用 `-C -` 来指定。 这点上话我觉得还是 curl 做的好一些，把选择的权利留给用户，这样子命令的使用会更加的灵活。

## 生成密码


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4NzczMzE4MiwxOTU2Njk3MTA0LC0yMD
E5MTc5ODUsLTU5MjcwMjY5NSwxNzk0OTU0NjgsLTQyOTczMTQy
MCwxNTM3ODYzMjI4LC0yNjYyNDA5MTYsLTEwNTYyOTYzODIsLT
MzNzEzMTk5LC0xODkxMDQwNjY0LDU1OTE3NTk5LC0xNzc1NzU1
MTI1LC0xNTIxOTkxNDIyLDQxNzIzMTI5MiwxNjM4Njc3MDI4LC
03ODg2MjM5OTcsMTE4MTI5OTk2OSw3MzA5OTgxMTZdfQ==
-->