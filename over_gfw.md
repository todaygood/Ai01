
# 外网资源

对我来说，科学上网很重要，下面罗列一下需要科学上网，我才能真正学习工作和生活的网站：

Youtube 和 Vimeo 上的各种大会和教学视频，除了我自己要学，我的孩子也要学。
Wikipedia 维基百科是我目前唯一信得过的百科全书，我在上面可以比较系统地翻阅各种词条。
SlideShare 上有很多的技术文档和资料的PPT，是我的知识学习的地方。
Quora 问答网站，在上面有很多有趣的问答。
博客和论文，很多博客和论文站点都被墙了，比如：Blogspot 和 Medium。
Google 的各种服务，比如：Gmail, Map, Docs，Driver，照片，图片搜索，Voices，论文搜索……包括Google官方的各种技术文档……
一些云服务，比如：Dropbox，IFTTT，Imgur，archive.org……
Twitter 上 Follow 一些牛人和一些官方账号，比如：AWS、Docker……
社交 Facebook, Telegram, Whatsapp, Slack……，有一些我在国外的亲戚和朋友……
Reddit 是一个聚合网站，一个新闻和文章的集散地，你可以认为是各种频道的今日头条……
Pinterest 和 Instagram 上面有很多不错的图片和视频新闻，是我减压力的地方……
新闻，如BBC。 BBC是全球比较出众的媒体，有太多的有价值资源和内容了，比如纪录片、学英文……
编程，有很多编程的场景需要翻墙，比如，Go语言编程时的 go get 中的很多库是放在 Google的服务器上， 然而Google是全部被墙，包括 Android 和其它一些文档和资源也是一样。包括 SourceForge 的某些项目也需要科学上网，Docker Registry也有部分被墙，还有偶尔抽风的Github，以及不能访问的gist……
……等等
所以，科学上网后，英文是一件很重要的事。

为什么这么说？这主要是针对计算机相关的知识，逻辑是这样的，如果你上了Google还是在用中文关键词，那么你好不容易出来了，结果又回去了，所以没什么意义。 换言之，科学上网的目的是为了进入广阔的世界范围与全世界的人交流，所以，英文是必备的，如果你英文有问题，VPN过去的用处也不大。

所以，我把这个前提条件放在第一的位置，就是说—— 真正的墙不是GFW，而是人的大脑！ 意思是，屏蔽你获得信息能力的不是墙，而很大一部分则是我们自己的语言能力！

## youtube 电子博主

[向北](https://www.youtube.com/@xiangbei)

[不一样的强哥](https://www.youtube.com/@DifferentMrQiang)

[不良林](https://www.youtube.com/@bulianglin)

[Hollis](https://www.youtube.com/@ProgrammerHollisG)

## 经济

[勃学家](https://www.youtube.com/@boist)


https://www.youtube.com/@talks1004

## 中国房市

https://www.youtube.com/@Lovetovisitthehouse



##  10.4 Cloudflare Warp 原生 IP
很多我们需要访问的网站都需要使用“原生 IP”，比如：Disney+， ChatGPT，New Bing 等。

所谓“原生 IP”就是指该网站的 IP 地址和其机房的 IP 地址是一致的，但是，很多 IDC 提供商的 IP 都是从其它国家调配来的，这导致我们就算是翻墙了，也是使用了美国的 VPS，但是还是访问不了相关的服务。所以，我们需要使用 Cloudflare Warp 来访问这些网站。

下面有几种安装方式：

全局模式。这种模式下，所有流量都会通过 Cloudflare 的网络，相当于VPN。
代理模式。通过在服务器本机启动一个 SOCKS5 代理，然后把需要的流量转发到这个代理上。

