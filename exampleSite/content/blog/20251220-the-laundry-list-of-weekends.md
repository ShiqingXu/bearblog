+++
title = "周末流水帐 1220"
date = "2025-12-20T20:38:05+08:00"
images = ["https://img.14says.xyz/2025/12/1766237862-20251220-the-laundry-list-of-weekends-banner.webp"]
tags = ["life"]

+++

![20251220-the-laundry-list-of-weekends-banner](https://img.14says.xyz/2025/12/1766237862-20251220-the-laundry-list-of-weekends-banner.webp)

昨晚睡了接近 8 小时，做了很多梦，不过现在都不记得了。8 点多醒来，看了一下睡眠记录，深度睡眠依旧不足 1 小时，不过倒也没有感觉没睡够，同时也没有感觉比较神清气爽。赖了一会儿床之后就起床洗漱，去工取电脑。

在工地处理了一会儿工作之后，忍不住去冲了一杯咖啡，喝完果然又有很大反应，心悸手抖恶心一条龙，明知自己会这样，还是没忍住喝了，突然有点儿理解抽烟的人为何忍不住了。不过区别是我并不是咖啡成瘾的症状，而是咖啡因不耐受，非要喝无非是馋了而已。

临近中午带上电脑回家，路上顺便去打了一会儿 Ingress，以及下了一单食物。今天是跟媳妇第一次约会的纪念日，当初吃的潮汕牛肉火锅，没法去圣地巡礼，于是买了点儿牛肉准备自己在家吃火锅。

今天气温其实比较高，出门时衣服和鞋子都穿得有点儿厚了，加上在路上走得比较快，回家时已经有点儿出汗了。休息了一会儿食物到了，就清洗了一下食物准备午餐了。掏出了露营用的折叠桌摆在沙发前面充当茶几，边看电视边吃。

下午看了 伊斯特伍德的电影 *[The Mule](https://www.imdb.com/title/tt7959026/?ref_=fn_t_1)*，看到最后半小时左右时想起来自己以前应该是看过，只是当时没怎么认真看，以至于几乎完全忘记看过了。作为一个贩毒主题的电影，里面出现的人名又是古斯塔沃又是索尔的，不知道是不是某种致敬。看完之后下午三点多，趁还有太阳，出门在小区里逛了一会儿。

回家时看到对门在搬家，其实从前段时间就感觉他们可能要搬走了，因为有一次看到他们网购了大纸箱子。由于入户门的隔音很差，回来之后一直能听到他们扯胶带的声音，只好播放音乐来掩盖。对面的房子是面向小区里面的，而我租的这个房子面向大马路，又吵又脏，不是很巧，不然能入住对面的话体验应该会比现在好一些。

重新安装了很久没用过的 ytdlp 和 ffmpeg，从[网上](https://luy.li/2025/12/14/yep_still_like_mp3/)抄了几行命令用于从 YouTube Music 上下载 mp3 音乐。尽管是 YouTube Music 会员，不过我还是更喜欢听本地音乐，并且由于我家的网络没有翻墙，因此 sonos 无法连接上 YouTube Music，不得不下载下来听了。

命令如下：

```
yt-dlp -x --audio-format mp3 \
  --audio-quality 0 \
  --embed-metadata --embed-thumbnail \
  --postprocessor-args "ExtractAudio:-q:a 0 -id3v2_version 3" \
  --postprocessor-args "FFmpegMetadata:-metadata comment=YouTubeID=%(id)s" \
  -o "%(artist,uploader)s-%(track,title)s.%(ext)s" \
  'the url'
```

晚饭时看了两集 Rick and Morty，感觉第 8 季比前面两三季都有意思一些。

在相册里翻找，希望找到一张适合今天的题图，意外发现了以前保存的一句 Lex Fridman 的 quote，打印出来贴在小黑板上了。

![20251220-the-laundry-list-of-weekends-lex-quote](https://img.14says.xyz/2025/12/1766238000-20251220-the-laundry-list-of-weekends-lex-quote.jpeg)
