我自制了一套程序员日历送给你
---

2018年在 V2 论坛大神出了本程序员日历（原贴在这里 https://www.v2ex.com/t/408428 ），之后图灵出版社还出限量版。pshu 看得自然技痒也自己做了本类似。每天一句计算机相关的名人名言，附带上名人的简介。样子是这样的：



先和大家分享下制作此日历用的一些技术，如果你只想下载日历，直接拉到底即可。

* React/Next.js
* Puppeteer
* cUrl
* excel / https://www.vicinitas.io/free-tools/download-user-tweets
* node.js



日历的样式的设计直接用的 web 技术。但是 pshu 其实是个前端技术的渣渣，勉强会有点 React，再加上觉得 webpack 配置太麻烦，就直接使用 Next.js。先用 mock 的数据画了个基本的页面。然后用 chrome 浏览器的打印到 pdf 的功能看了下效果，基本满意就开始爬数据了。

日历日期数据的话随便找个在线的日历服务即可。这里有个小坑就是 pshu 用请求库 `superagent` 模拟请求，服务端总是拒绝我。后来直接在 chrome 控制台，把网络请求 copy as cUrl；然后根据规律批量生成 shell 命令执行爬下网页离线分析。

接下来是名人名言了，本来是想爬这个推特号的；后来转念一想，twitter 不是有 open api 的嘛，直接调用 api 来的多大方爽快啊。结果申请的时候我又觉得麻烦了，放弃了。最后直接 google，“download tweets of a user”，一堆现成的服务，随便选了一个授权下直接所有的推文都变成 excel 下载下来。

之所以用的 tweet 的中名言数据是看中每个推下面有 like 的统计，这样就可以帮我筛选出那些能够打动到程序员内心的名言了；既然是 excel 通过简单筛选排序，整理下文字，然后导出 cvs 。

![code wisdom](http://cdn2.51ulong.com/18-11-9/94816503.jpg)

最后就是名人简介了，google 搜索名人的时候会出现下面这样的开放数据的面板![](http://cdn2.51ulong.com/18-11-10/55195630.jpg)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ5NjI0MDUxNiwtOTkyNDY3Mzc5LC0xMj
E1MjQ4Nzg5LDg4NDY3MTgzNywxNTk1NTgyNzg2LDEzNjAzMzY2
MTIsLTI2NjI0Njg5MCwtMTU2NDc2MzgzNiw4Mjc5OTQwMjcsNz
Y0NDkxOTU4XX0=
-->