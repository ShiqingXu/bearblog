+++
title = "记一次 macOS 的内存泄露"
date = "2025-12-04T22:05:31+08:00"
images = ["https://img.14says.xyz/2025/12/1764857277-20251204-on-a-memory-leak-on-macos-banner.png"]
tags = ["software","折腾",]

+++

![20251204-on-a-memory-leak-on-macos-banner](https://img.14says.xyz/2025/12/1764857277-20251204-on-a-memory-leak-on-macos-banner.png)

近期遭遇了一次 macOS 的突然卡死，弹出来的提示是 `强制退出应用程序：系统的应用程序内存不足，若要避免你的电脑出现问题，请退出你未在使用的所有应用程序`，我一看，好家伙，Infuse 占了 56.67GB 的内存，几乎所有程序的状态都变成已暂停了。

好家伙，这是遭遇内存泄露了。我试图强制退出各种应用，但是没有一个程序有反应，都是只会转菊花，最终不得已强制关机重启才解决问题。印象中，这应当是我第一次遭遇内存泄露。

有在网上看到过多次网友吐槽 macOS 自带的各种软件引起内存泄露的案例，考虑到近几年来 macOS 越来越不稳定的事实，倒是也不难理解。不过我这次漏的看上去是 infuse，截图问了一下 AI，AI 认为是 Infuse 的锅的概率比较大。

Jonathan Blow 的演讲又在耳边回响。
