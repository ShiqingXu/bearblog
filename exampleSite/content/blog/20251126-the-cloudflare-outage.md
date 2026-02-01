+++
title = "也被 Cloudflare 宕机影响了"
date = "2025-11-26T21:40:23+08:00"
images = ["https://img.14says.xyz/2025/11/1764164524-20251126-the-cloudflare-outage-banner.png"]
tags = ["software"]

+++

![20251126-the-cloudflare-outage-banner](https://img.14says.xyz/2025/11/1764164524-20251126-the-cloudflare-outage-banner.png)

上周有一天，晚上回家例行更新本站的时候，发现站点无法访问了，我以为是自己前一次的更新出了什么问题。仔细一看错误提示，是 Cloudflare 的 Internal server error，此前我并没有见过这个错误提示，并不确定是不是真的内部错误。

事后 Cloudflare 公布了[事件的详细过程](https://blog.cloudflare.com/18-november-2025-outage/)。

然后随手打开了 Twitter，试了几次发现都上不去，不论手机上还是电脑上，这才意识到可能真的是Cloudflare 坏掉了。我照常写好了当天的内容，照常push到GitHub上，没有遇到什么错误。过了一段时间修好了，看了一下没有成功发布，于是重新运行了一遍GitHub actions。

印象里近期发生过好几次云服务商故障导致大面积服务不可用的事情了，上一次大约是6月份Google Cloud的服务中断事件，也是影响了大量的线上服务，可能会有很多依赖这些云服务的企业因此蒙受巨大的损失。

以前遇到这种事情，顶多是自己日常使用的服务用不了。这次自己搭建在Cloudflare上的博客也受到了波及，还是第一次。

每当这种时候，互联网上就会出现这张梗图，以及其各种变体。不免让人再次想起Blow的演讲，阻止文明的坍塌。

![20251126-the-cloudflare-outage-meme](https://img.14says.xyz/2025/11/1764164679-20251126-the-cloudflare-outage-meme.png)

自建博客比起使用平台服务来说，麻烦很多，每次写作、推送、部署的流程很麻烦，而且还要解决图床问题。为了避免免费的 R2 Bucket空间用尽，每次上传图片前还得手动压缩一下。但即使这么麻烦，我还是更喜欢自建，一个很重要的原因是觉得数据掌握在自己，而不是某个平台的手里。这次事件使我意识到，哪有什么掌握在自己手里的数据。

当然，这也不意味着我会因此转向在某个平台上写作，毕竟这只是其中一个原因而已。
