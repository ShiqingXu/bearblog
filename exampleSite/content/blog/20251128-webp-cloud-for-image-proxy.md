---
title: 使用 WebP Cloud 服务为图片进行代理
date: 2025-11-28 08:20:25
tags: [blog, software, 折腾]
---

此前为了优化站点，尤其是图片的访问速度，把图片托管方案从直接放置在 GitHub 仓库里变更为了使用 Cloudflare R2 Bucket 作为图床的方案，速度提升了很多，并且也使得源文件仓库得以瘦身，未来也不会随着时间的推移逐渐因为图片原因变得体积飞速膨胀。



不过这依然不够快，寻找方案时发现了 [WebP Cloud Services](https://webp.se/) 这个服务，可以在牺牲一小部分图像质量的情况下大幅压缩图片的体积，并进行缓存，从而提升加载速度。此外还有诸如为图片添加水印等服务，不过我都用不上。

![webp-cloud-watermark-services](https://img.14says.xyz/2025/09/1758587446-webp-cloud-watermark-services.png)

每日有免费的 3000 个请求额度和 200M 缓存，并且每日签到还可以获得一些永久额度。对于我这个无人问津的站点来说，3000 额度个足够了。如果不够，可以设置为超额后访问原始图片链接，也可以选择订阅方案，非常便宜。

![webp-cloud-pricing](https://img.14says.xyz/2025/09/1758587295-webp-cloud-pricing.png)

## 设置方法

### 创建代理

在主页上点击创建代理，选择服务器地址，填写代理名称及原站地址，也即图片托管的服务器地址。我这里填写的是 R2 Bucket 绑定的二级域名，然后选择一下代理模式，点击完成即可。

![webp-cloud-create-proxy-1](https://img.14says.xyz/2025/09/1758587360-webp-cloud-create-proxy-1.png)

![webp-cloud-create-proxy-2](https://img.14says.xyz/2025/09/1758587373-webp-cloud-create-proxy-2.png)

## 集成到站点配置文件



创建好代理之后，点击集成指南页面，选择自己的站点方案，我这个选的是 Hexo，右边会给出集成的方案。

![webp-cloud-proxy-config](https://img.14says.xyz/2025/09/1758587393-webp-cloud-proxy-config.png)

先是安装一个名为`hexo-webp-cloud-proxy`的包，然后在配置文件中添加相应的配置信息即可，之后就可以正常构建网站了。

## 一个小坑

配置文件里列出了四种图片格式，这个格式其实是大小写敏感的。我有几张图片是在 Windows 电脑上通过浏览器访问 iCloud 导出的，其扩展名是大写的 JPEG，这几张图片就没有被成功代理，只好在代理格式列表里把大写也加入了进去。

同一张照片，在 macOS 的 photos app 上导出来扩展名就是小写，在 Windows 上通过浏览器导出来就是大写，不知道苹果是什么逻辑。

## 效果

设置完重新部署网站之后，打开生成的 HTML 页面源码，可以看到图片地址顺利被转换。

![webp-cloud-request-analysis](https://img.14says.xyz/2025/09/1758587407-webp-cloud-request-analysis.png)
