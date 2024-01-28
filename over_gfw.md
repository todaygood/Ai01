
# 外网资源

对我来说，科学上网很重要，下面罗列一下需要科学上网，我才能真正学习工作和生活的网站：



## youtube 电子博主

[向北](https://www.youtube.com/@xiangbei)

[不一样的强哥](https://www.youtube.com/@DifferentMrQiang)

[不良林](https://www.youtube.com/@bulianglin)

[Hollis](https://www.youtube.com/@ProgrammerHollisG)

[现任明教教主](https://www.youtube.com/@user-iu8pq5bh7u)

1. https://aitechtogether.com/

2. https://luminous-mapusaurus-1aa.notion.site/Mobile-Aloha-7427f27eb6d1495aa8d07e4be2aa8471

## IP地址

https://ipinfo.io/


比特浏览器

開始流覽

設置完成後，你就可以開始使用比特指紋流覽器進行網路流覽了。這時候你會發現，無論你訪問哪個網站，都無法獲取到你的真實IP地址和設備資訊。這就意味著，你的網路行為無法被追蹤



##  10.4 Cloudflare Warp 原生 IP
很多我们需要访问的网站都需要使用“原生 IP”，比如：Disney+， ChatGPT，New Bing 等。

所谓“原生 IP”就是指该网站的 IP 地址和其机房的 IP 地址是一致的，但是，很多 IDC 提供商的 IP 都是从其它国家调配来的，这导致我们就算是翻墙了，也是使用了美国的 VPS，但是还是访问不了相关的服务。所以，我们需要使用 Cloudflare Warp 来访问这些网站。

下面有几种安装方式：

全局模式。这种模式下，所有流量都会通过 Cloudflare 的网络，相当于VPN。
代理模式。通过在服务器本机启动一个 SOCKS5 代理，然后把需要的流量转发到这个代理上。

