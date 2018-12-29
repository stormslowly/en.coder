我花2个小时做了个新年倒计时给你
---

忙忙碌碌一年就要到头了，作为程序员到了明年还得继续改今年写的 bug。但好歹是跨年还是要搞点仪式感才行。

在闲逛的时候看到了，一个在终端实现的2019新年倒计时。
![command line magic](http://cdn2.51ulong.com/18-12-29/67719352.jpg)

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
$figlet hello
 _          _ _
| |__   ___| | | ___
| '_ \ / _ \ | |/ _ \
| | | |  __/ | | (_) |
|_| |_|\___|_|_|\___/

```
为了在 mac 上也能搞个倒计时，我就决定用 H5 实现一个。大家也知道，我是一个前端渣渣，会点简单的 React。不想麻烦的配置的 webpack 就直接用了 Gatsby.js。NPM 上呢也有纯 Javascript 实现的 figlet。简单的拼装了下就作出了

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MTM4NTkwOTQsMTQ0MzkwNDI0OF19
-->