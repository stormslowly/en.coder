我自制了一套程序员日历送给你
---

2018年在 V2 论坛大神出了本程序员日历（原贴在这里 https://www.v2ex.com/t/408428 ），之后图灵出版社还出限量版。pshu 看得自然技痒，也做了本2019年的程序员日历。每天一句计算机相关的名人名言，附带上名人的简介。样子是这样的：

![calendar](http://cdn2.51ulong.com/18-11-10/22054520.jpg)

那就大家分享下制作此日历用的一些技术，如果你只想下载日历，直接拉到底即可。

* React/GatsbyJS
* Puppeteer
* cUrl
* excel / https://www.vicinitas.io/free-tools/download-user-tweets
* node.js/ Typescript

日历的排版设计直接用的 Web 技术。但是 pshu 其实是个前端技术的渣渣，勉强会有点 React，再加上觉得 webpack 配置太麻烦，就直接使用 GatsbyJS。先用 mock 的数据画了个基本的页面，然后用 chrome 浏览器的打印到 pdf 的功能看了下效果，基本满意就开始爬数据了。

日历日期数据的话随便找个在线的日历服务即可。这里有个小坑就是 pshu 用请求库 `superagent` 模拟请求，服务端总是拒绝我。后来直接在 chrome 控制台，把网络请求 copy as cUrl；然后根据规律批量生成 shell 命令执行爬下网页离线分析。

接下来是名人名言了，本来是想爬这个推特号的；后来转念一想，twitter 不是有 open api 的嘛，直接调用 api 来的多大方多爽快啊。结果申请的时候我又觉得麻烦了，放弃了。最后直接 google，“download tweets of a user”，一堆现成的服务，随便选了一个，授权下，所有的推文 excel 格式下载下来。

![code wisdom](http://cdn2.51ulong.com/18-11-9/94816503.jpg)
之所以用 tweet 上的名言数据是看中每个推下面有 like 的统计，这样就可以帮我筛选出那些能够打动程序员内心的名言了；既然是 excel 通过简单筛选排序，整理下文字，然后导出 cvs 。

最后就是名人简介了，google 搜索名人的时候会出现下面这样的开放数据的面板，正是我想要的。爬 google 这件事情倒是不难，用 puppeteer 轻松就解决了。但 pupeteer 是 google 出的 headless 浏览器， 爬起来有种 ***师夷长技以制夷*** 的喜感。
![open data](http://cdn2.51ulong.com/18-11-10/55195630.jpg)

最后把日期数据和名人名言信息合并成 JSON，制作日历数据就有了。接着使 `gatsby-transformer-json`, 利用 gatsby 的 api 一张日历一个页面。再利用 puppeteer 的把2019年的页面都打印成 pdf，最后用 macOs 自带的 pdf 合并工脚本合成日历文件，就大功告成了。

```bash
sudo ln "/System/Library/Automator/Combine PDF Pages.action/Contents/Resources/join.py" PDFconcat

PDFconcat  --output calendar.pdf 2019*.pdf
```

日历的下载
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY1NjY1NjczLC00MDA4ODY4MTUsMjU1MT
MxOTA2LDI1NTU5MDc3MCw1MTA3NjIzMjIsLTEyMzAzMDQzOTcs
LTk5MjQ2NzM3OSwtMTIxNTI0ODc4OSw4ODQ2NzE4MzcsMTU5NT
U4Mjc4NiwxMzYwMzM2NjEyLC0yNjYyNDY4OTAsLTE1NjQ3NjM4
MzYsODI3OTk0MDI3LDc2NDQ5MTk1OF19
-->