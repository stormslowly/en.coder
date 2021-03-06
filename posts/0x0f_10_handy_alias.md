10个好用的 bash 别名
----

上一篇推文讲了，程序员要巧干不要蛮干，注重效率提高。今天再分享一篇提升“微效率”的文章。原文标题：《10 handy Bash aliases for Linux》，原文地址 https://opensource.com/article/18/9/handy-bash-aliases 。p叔觉得有几个别名还是挺有用的。文章用的单词和句子都比较简单，大家可以尝试直接看看原文。文章开头有两个单词 *condense* 和 *cryptic* 用得很地道就翻译个开头。

>How many times have you repeatedly typed out a long command on the command line and wished there was a way to save it for later? This is where Bash aliases come in handy. They allow you to ***condense*** long, ***cryptic*** commands down to something easy to remember and use. Need some examples to get you started? No problem!

有些很长的命令敲得多了，是不是很想有个地方保存在这个命令，下次用就能节省很多时间。Bash 的别名（alias）就是用来做这个的，让冗长的命令变得简短  *(原文用了 condense，凝结这个单词用来表示命令缩短了，这里 pshu 意译了下 )*，晦涩难用的变得简单易用*(cryptic原意是神秘的意思；程序员常见的变形是 crypto，加密 cryptograph 的简写；有些命令确实难用的就像加密了一样 )*。直接给你们上例子。

 原文中还顺便提了下，如果你要修改 bash 别名的话是要编辑  `bash_profile`  这个文件。这些基础的东西 pshu 就带过了。如果不知道的可以去看下原文。

## tar 
来的第一个例子就是要解决 cryptic command `tar` 命令。
给出的别名 `alias  untar='tar -zxvf '` 这几个命令行选项是什么意思先不说，我们先看一个 xkcd 的漫画(https://xkcd.com/1168/) 就知道 tar 是有多 cryptic。它是一个不 google 你用不好的命令。

![xkcd  tar](http://cdn2.51ulong.com/18-11-1/42769127.jpg)

不过要想记住还是有方法，下面这个咆哮体就能帮你记住。记住了就不要用这个别名了，下次直接可以在其他同事面前炫技了。：p

![咆哮法记 tar 用法](http://cdn2.51ulong.com/18-11-1/56585117.jpg)

## wget

`wget` pshu用的比较少（其实是没怎么用），为了看下 wget 的手册还安装了下。`alias  wget='wget -c '` 命令可以帮在下载中断后恢复下载。这里这个 c 就是***continue***的意思。

![curl vs wget ](http://cdn2.51ulong.com/18-11-2/31464466.jpg)

pshu常用的下载命令是`curl`, curl 对应的选项是 `-C, --continue-at <offset>` , 是要通过 offset 来指定继续下载的位置。如果要自动获取 offset 的话只要使用 `-C -` 来指定。 这点上话我觉得还是 curl 做的好一些，把选择的权利留给用户，这样子命令的使用会更加的灵活。

## 生成密码

> Need to generate a random, 20-character password for a new online account? No problem.

需要给新用户生成一个20位的密码？没问题。
```
alias getpass="openssl rand -base64 20"
```
这里 pshu 要做一个简单的勘误。这个***20***是表示随机生成20个字节；`-base64` 是表示对这些字节做 base64编码。所以命令出来的密码长度并不是20。这个大家可以试试。如果大家对出现的密码中末尾有`=` 比较纠结的话，可以把20改成被3乘除的数字就可以了。至于为什么，看看 base64 的 wiki 就知道了。

## 文件完整性校验

```
alias  sha='shasum -a 256 '
```
pshu 其实自己对下载的文件做校验也没有这个习惯，下次下载的时候记得用这个试试看了。

## ping 

*nux 系统上的 ping 命令是 ping 到天荒地老的。windows 上的 ping 是默认 3次的。如果想变得和 windows 上一样的可以用这个别名，不过记得把5改成3。
```
alias  ping='ping -c 5'
```

## 马上要一个 web 服务器

来咯! 不过区分下你的默认的 python 的版本。如果是 py3的话，记得用下面那个。不过 pshu 建议的话 还是不要指定端口，8000 是默认的端口；如果把8000去掉，直接可以用 `www 9527` 来指定任意端口了。刚才还说呢，把选择留给用户！

```
alias  www='python -m SimpleHTTPServer 8000'
```
```
alias www='python -m http.server 8000'
```

## 测速

实现需要下载一个 speedtest-cli 的脚本到你的 PATH 目录下 ；然后再做个别名。你看 wget 马上就用上了。

```
wget -O speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py
chmod +x speedtest-cli
```

`alias  speed='speedtest-cli --server 2406 --simple'`。 pshu 测试了下，测速的时候会就近选取测速点，出来的数据还是蛮合理的，可用！


## 外网 IP

作为程序员通过 web 浏览器看外网 IP 是可耻的。赶紧做上这个别名吧！
`alias  ipe='curl ipinfo.io/ip'`。这次用的 curl 。不过 ipinfo.io 的 ip 服务器非常的不稳定，经常因为中国特色网络而访问超时。如果大家有什么替代方案的话，欢迎留言告诉 pshu了。

## 内网 IP

`alias  ipi='ipconfig getifaddr en0'` 
不过大家记得把 en0 换成自己实际使用的网卡即可。比如我用的是 `en1`。

## 清屏

`alias  c='clear'`。这个别名，pshu 觉得做不做都无所谓。因为 bash 自带的清屏快捷键 `ctrl+l`

好了，10个 alias 就给大家介绍到这里。希望对家有用。对了原文作者是一个老程序了，还有一些关于 linux 使用的文章，看看老前辈怎么用 linux，还是有点收获的。

最后如果你有什么 linux 使用上的神兵利器也可以留言分享给 pshu。
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDg2MTY3MDM5LC04MjA3MDQ3NywtMTU4Nz
c1NDU2NywtMTAxMzU1MDM0Miw0NzI5NjMzNTQsLTE1MDYwNzkx
MjIsLTE2OTcyOTEzMTUsLTExNTY3OTIwMDUsMTAyNzM3Njg4LC
04OTEzOTM5MzUsMTgxODM0MDI3NiwtMTU0OTMxNDAxMSwxMzQ4
MzE2ODU2LDgwNzgxMzA4MiwxNjMxODI3NzUxLDEwNDU1ODUzNz
EsMTk1NjY5NzEwNCwtMjAxOTE3OTg1LC01OTI3MDI2OTUsMTc5
NDk1NDY4XX0=
-->