# rule_for_quantumultX
自用圈X规则，GithubAction定期自动从上游拉取资源整合更新，部分手动维护
* **去广告**
```ruby
去广告重写开启后请先清除缓存,QuantumultX重写需配合ReFix修正规则
```
 > - [x] 一般化广告
 > - [ ] spotify去广告加强
 > - [x] youtube去广告加强(香港节点效果最好,已修正短视频无法播放)
 > - [x] 书旗小说去广告(规则与重写较多,可能误杀,文章内‘全场畅读无广告’清除缓存无效请卸载重装书旗)
 > - [x] 番茄小说去章内末广告(且用且珍惜)
 > - [x] 每日优鲜、百度地图开屏广告屏蔽(不起作用先清缓存)
 > - [x] 百度云盘广告屏蔽(会员与非会员开屏广告不同，测试的是会员，可能需要重装app)
。。。。

***ps:***
-->[详细广告屏蔽列表](https://github.com/zqzess/rule_for_quantumultX/blob/master/AdBlockList.md)
 
 ```ruby
发现Mitm会造成ssl错误(code:9829)导致番茄小说报证书，如遇此请先关闭Mitm加载再开启Mitm!
```
## 项目地址
[github](https://github.com/zqzess/rule_for_quantumultX)
[gitee](https://gitee.com/zqzess/rule_for_quantumult-x)
[我的博客](https://www.whitemoon.top)

[推荐一套彩色图标](https://github.com/Semporia/Hand-Painted-icon)
## 目录
```ruby
 谷歌搜索重定向已经整合至重写规则
```
- ->~~[Google搜索中国，香港，日本重定向](./谷歌搜索重定向.md)~~
- ->[分流规则添加](#分流规则添加)
- ->[重写规则](#重写规则)
- ->[完整配置文件](#完整配置文件)
- ->[Loon配置文件](#Loon配置文件)
- ->[Surge配置文件](#Surge配置文件)
- ->[参考](#参考)
### 分流规则添加
<details>

```
[policy]

url-latency-benchmark=♻️ 自动选择, server-tag-regex=(?=.*)^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Auto.png
static=🚀 手动切换, resource-tag-regex=.*, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Static.png
round-robin=🔮 负载均衡, server-tag-regex=.*, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Round_Robin.png

#节点地区分类
static=🇭🇰 香港节点, server-tag-regex=(?=.*(香港|HK|(?i)Hong))^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Hong_Kong.png
static=🇯🇵 日本节点, server-tag-regex=(?=.*(日本|JP|(?i)Japan))^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Japan.png
static=🇺🇲 美国节点, server-tag-regex=(?=.*(美国|美國|洛杉矶|西雅图|费利蒙|US|(?i)States|American))^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/United_States.png
static=🇨🇳 台湾节点, server-tag-regex=(?=.*(台湾|台灣|TW|(?i)Taiwan))^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/TW.png
static=🇰🇷 韩国节点, server-tag-regex=(?=.*(韩国|韓國|南朝鲜|KR|(?i)Korean))^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Korea.png
static=🇷🇺 俄罗斯节点, server-tag-regex=(?=.*(俄罗斯|俄羅斯|RU|(?i)Russia))^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://cdn.jsdelivr.net/gh/Koolson/Qure@master/IconSet/Russia.png
static=🇸🇬 新加坡节点, server-tag-regex=(?=.*(新加坡|狮城|SG|(?i)Singapore))^((?!(专线|手游|游戏|(?i)IPLC|IEPL|game)).)*$, img-url=https://cdn.jsdelivr.net/gh/Koolson/Qure@master/IconSet/Singapore.png

# 其中 CMedia 策略组为中国媒体，GMedia 为国际媒体，Outside 为境外链接，Mainland 为大陆链接，Others 为最终规则
static=AdBlock, reject, direct, img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/AdBlock.png
static=Apple, direct, Outside, 🚀 节点选择,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Apple.png
static=AppleIOSUpdate, reject, direct,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Apple.png
static=Microsoft, direct, Outside, 🚀 节点选择,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Microsoft.png
static=Netflix, Outside, direct, 🚀 节点选择,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Netflix.png
static=YouTube, Outside, direct, 🚀 节点选择,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/YouTube.png
static=GMedia, Outside, direct, 🚀 节点选择,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/GMedia.png
static=CMedia, direct, proxy, img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/CMedia.png
static=Speedtest, Outside, direct, 🚀 节点选择,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Speedtest.png
static=Outside, proxy, direct, ♻️ 自动选择,🔮 负载均衡,🚀 手动切换,🇭🇰 香港节点,🇯🇵 日本节点,🇨🇳 台湾节点,🇺🇲 美国节点,🇰🇷 韩国节点,🇷🇺 俄罗斯节点,🇸🇬 新加坡节点,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Outside.png
static=Mainland, direct, proxy, img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Mainland.png
static=Others, Outside, direct, ♻️ 自动选择,🔮 负载均衡,🚀 手动切换,🇭🇰 香港节点,🇯🇵 日本节点,🇨🇳 台湾节点,🇺🇲 美国节点,🇰🇷 韩国节点,🇷🇺 俄罗斯节点,🇸🇬 新加坡节点,🚀 节点选择,img-url=https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/IconSet/Others.png
```
```
[filter_remote]
#规则分流修复
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/ReFix.list, tag=ReFix规则修正, update-interval=86400, opt-parser=false, enabled=true
#自定义
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/AdBlock.list, force-policy=AdBlock,tag=AdBlock , enabled=true
#苹果服务
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/Apple.list, force-policy=Apple,tag=Apple , enabled=true
#苹果ios更新屏蔽
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/AppleIOSUpdate.list, force-policy=AppleIOSUpdate,tag=AppleIOSUpdate,enabled=true
#微软
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/Microsoft.list, force-policy=Microsoft,tag=Microsoft , enabled=true
#奈飞
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/Netflix.list, force-policy=Netflix,tag=Netflix , enabled=true
#油管
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/YouTube.list, force-policy=YouTube,tag=YouTube , enabled=true
#spotify
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/StreamingMedia/Music/Spotify.list, tag=Spotify, force-policy=Spotify, update-interval=86400, opt-parser=false, enabled=true
#国际媒体
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/GMedia.list, force-policy=GMedia,tag=GMedia , enabled=true
#国内媒体
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/CMedia.list, force-policy=CMedia,tag=CMedia , enabled=true
#speedtest测速
https://raw.githubusercontent.com/GeQ1an/Rules/master/QuantumultX/Filter/Speedtest.list, force-policy=Speedtest,tag=Speedtest , enabled=true
#国外网站
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/Outside.list, force-policy=Outside,tag=Outside , enabled=true
#大陆
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rules/Mainland.list, force-policy=Mainland,tag=Mainland , enabled=true
```
```
[filter_local]
host-suffix, local, direct
ip-cidr, 10.0.0.0/8, direct
ip-cidr, 17.0.0.0/8, direct
ip-cidr, 100.64.0.0/10, direct
ip-cidr, 127.0.0.0/8, direct
ip-cidr, 172.16.0.0/12, direct
ip-cidr, 192.168.0.0/16, direct
geoip, cn, Mainland
final, Others
```
</details>

### 重写规则

<details>

自用的重写规则

</br>**功能**:
- 有兔(米兔)阅读羞耻的开屏广告图片
- Google搜索中国，香港，日本重定向
- YouTuBe跳广告
- 书旗小说去广告(规则与重写较多,可能误杀)
- 番茄小说去章末广告(且用且珍惜)
- 每日优鲜、百度地图开屏广告屏蔽(不起作用先清缓存)
- 部分规则通用，经测试，今日头条小说与米读小说章内广告也能屏蔽
- 百度云盘广告屏蔽(会员与非会员广告开屏不同，测试的是会员，可能需要重装app)
。。。。。

***ps:***
-->[详细广告屏蔽列表](https://github.com/zqzess/rule_for_quantumultX/blob/master/AdBlockList.md)

**搬运**:
 - 抖音去广告 (By Choler)
 - 去微信公众号广告 (By Choler)
 - 酷我音乐SVIP (By yxiaocai)
 - 爱美剧Vip (by huihui）(官网：app.meiju2018.com)
 - 京东淘宝比价 (by yichahucha)
 - 香蕉视频VIP (by NobyDa)
 - 91短视频 (by NobyDa)
 - PicsArt美易 pro (by NobyDa)
 - 哔哩哔哩番剧开启1080P+ （by NobyDa）

</details>

```
[rewrite_remote]
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rewrite/MyRewrite.conf, tag=zqzess自用rewrite, update-interval=86400, opt-parser=false, enabled=true
#youtube广告
https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/rewrite/youtube.qxrewrite, tag=youtube广告屏蔽, update-interval=86400, opt-parser=false, enabled=true
```
### 完整配置文件
**两个版本配置文件均无定时任务**
- [简洁版-->](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/zqzess_lite.conf)
- [策略组复杂带节点地区分类-->](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/QuantumultX/zqzess.conf)

**使用方法：**
Quan X主界面，点击右下角风车，然后弹出界面下拉至 配置文件-下载，点击下载,将任一配置文件地址粘贴

```ruby
PS:
 要开启重写功能需先配置证书并信任再开启MitM证书
```
### Loon配置文件
- [完整配置文件](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/zqzess_Loon.conf)
- [脚本订阅](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/js/js.conf)
- [复写订阅](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Rewrite/zqzess_Rewrite.conf)
- [广告屏蔽插件](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Plugin/AdBlock.plugin)
- [哔哩哔哩增强插件搬运整合](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Plugin/bilibili.plugin)
- [酷我增强插件整合](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Plugin/kuwo.plugin)
- [知乎增强插件搬运整合](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Plugin/zhihu.plugin)
- [百度系广告屏蔽](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Plugin/BaiduAdBlock.plugin)
- [波点音乐mv屏蔽](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Plugin/bodianMusic.plugin)
- [youtube广告屏蔽](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Loon/Plugin/YouTubeAd.plugin)

### Surge配置文件
- [完整配置文件](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/zqzess_surge.conf)
- [广告屏蔽模组](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/AdBlock.sgmodule)
- [哔哩哔哩增强插件搬运整合](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/bilibili.sqmodule)
- [酷我增强插件整合](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/kuwo.sgmodule)
- [知乎增强插件搬运整合](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/zhihu.sgmodule)
- [百度系广告屏蔽](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/BaiduAdBlock.sgmodule)
- [波点音乐mv屏蔽](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/bodianMusic.sgmodule)
- [safari全能聚合搜索-百度搜索引擎版](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/Qsearch.sqmodule)
- [Peng-YM油猴脚本转换器surge订阅修正版](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/GreasyFork.sgmodule)
- [youtube广告屏蔽](https://raw.githubusercontent.com/zqzess/rule_for_quantumultX/master/Surge/Module/YouTubeAd.sgmodule)
 
surge搬运：
- [高级订阅管理工具-必装](https://raw.githubusercontent.com/Peng-YM/Sub-Store/master/config/Surge.sgmodule)
- [NetFlix显示IMDB评分](https://kinta.ma/surge/netflix_rating.sgmodule)
- [BoxJs](https://raw.githubusercontent.com/chavyleung/scripts/master/box/rewrite/boxjs.rewrite.surge.sgmodule)
- [TextFight区域限制解除](https://raw.githubusercontent.com/NobyDa/Script/master/Surge/Module/TestFlightDownload.sgmodule)
  
### 参考鸣谢
- [@h2y](https://github.com/h2y)
- [@blackmatrix7](https://github.com/blackmatrix7/ios_rule_script)
- [@jdlingyu](https://github.com/jdlingyu/ad-wars/blob/master/hosts)
- [@Tartarus2014](https://github.com/Tartarus2014/QuantumultX-Script)
- [@GeQ1an](https://github.com/GeQ1an/Rules/tree/master)
- [@Koolson](https://github.com/Koolson/Qure)
- [@NobyDa](https://github.com/NobyDa/Script)
- [@TributePaulWalker](https://github.com/TributePaulWalker/Profiles)
- [@Peng-YM](https://github.com/Peng-YM)
- [@lhie1](https://github.com/lhie1/Rules)

### 访问量

![](http://profile-counter.glitch.me/zqzess/count.svg)

## 项目 Star 数增长趋势

[![Stargazers over time](https://starchart.cc/zqzess/rule_for_quantumultX.svg)](https://starchart.cc/zqzess/rule_for_quantumultX)
