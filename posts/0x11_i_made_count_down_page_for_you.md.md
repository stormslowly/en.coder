我花2个小时做了个新年倒计时给你
---

忙忙碌碌一年就要到头了，作为程序员到了明年还得继续改今年写的 bug。但好歹是跨年还是要搞点仪式感才行。

在闲逛的时候看到了，一个在终端实现的2019新年倒计时。
![command line magic](http://cdn2.51ulong.com/18-12-29/67719352.jpg)

shell 脚本整理如下：
```bash
while [[ $(date +%Y) -ne 2019 ]];
do 
  figlet $(($(date -d 2019-01-01 +%s)-$(date +%s)));
  sleep 1;
  clear;
done;
figlet 'Happy New Year!'
```
shell 执行的结果确实很炫酷，但是只能在 linux 主机上执行。在我的 MacOS 上就不行了。主要是 MacOS 的 `date`  和 linux/unix 不同。而 `figlet`这个命令通过`brew install figlet`安装，试试效果不错！

```bash
$figlet 2019
 ____   ___  _  ___
|___ \ / _ \/ |/ _ \
  __) | | | | | (_) |
 / __/| |_| | |\__, |
|_____|\___/|_|  /_/

```
为了在 mac 上也能搞个倒计时，我就决定用 H5 实现一个。大家也知道，我是一个前端渣渣，会点简单的 React。不想麻烦的配置的 webpack 就直接用了 Gatsby.js。NPM 上也有纯 Javascript 实现的 figlet。简单的拼装了下就作出了这个H5的新年倒计时了。

![H5 countdwn](http://cdn2.51ulong.com/18-12-29/30949467.jpg)

如果你恰好要守着跨年这一刻，不妨用用这个 pshu 的这个倒计时。

https://2019.shupengfei.me/  点击原文可达。

项目地址：<https://github.com/stormslowly/countdown>

好了，最后说下这个 figlet这个工具。其实它应该写做 FIGlet，这个 let 是 letter 的简写，而 FIG 是 Frank, Ian and Glenn ，三个人的名字的简写。之所会有 figlet 工具，就是因为 Frank 邮件签名中使用了 ASCII 码拼成的名字，然后这三位 Geek 就开始开发这个工具了，第一个版本的 figlet（其实当时叫newban） 用 C 写成只有170行。到了现在的figlet 已经有1700多行代码，支持140多种字体。

好了，这是2018年的最后一篇文章了，希望大家喜欢，最后祝大家新年快乐。
明年见。首字母。这个工具的诞生就是源于 Frank 在他的邮件
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzUwMTUyOTYzLDk0NjE3NTgyMywtNzIwMT
gyNDIyLC05MDExODg1NDgsNjA3MDk0NjMsMTMwNzM0OTIyMSw4
ODI3NTk5NTYsODc2MzI3MDUwLDE3NTMzMzM3NTAsMTQ0MzkwND
I0OF19
-->