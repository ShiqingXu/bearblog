+++
title = "Raycast for Windows Update"
date = "2026-01-09T20:33:29+08:00"
images = ["https://img.14says.xyz/2026/01/1767963514-20260109-raycast-for-windows-update-banner.webp"]
tags = ["software", "折腾"]

+++

![20260109-raycast-for-windows-update-banner](https://img.14says.xyz/2026/01/1767963514-20260109-raycast-for-windows-update-banner.webp)

Raycast for Windows 公测版用了一段时间了，一直没有检查过更新，前两天顺手点了一下检查更新，提示说已经是最新版，也就没有再管。结果今天看到新闻说更新到什么版有了什么新功能，看到版本号比我的已经超前好几个了，于是再次去检查，依然提示没有更新。

试图到官网下载安装包，结果官网已经不直接提供可执行文件的下载了，而是会跳转到微软商店进行下载，看起了这是未来主要的分发渠道了。不巧的是我们工地的电脑统一装的 LTSC 版本的 win10，并不包含微软商店组件，因此无法安装。

看到 Raycast 官网上还提供了 winget 命令安装的方式，试了一下也提示说当前已经是最新版，没有可用的更新，这就有点儿奇怪了。

研究了一番，可以通过[这个网站](https://store.rg-adguard.net/)把微软商店里的安装包下载回来，把 Raycast 的微软商店链接丢进去，会返回一个文件列表，选择图中最后面一个.msix 文件下载下来即可。

![20260109-raycast-for-windows-update-list](https://img.14says.xyz/2026/01/1767962918-20260109-raycast-for-windows-update-list.webp)

这个格式的文件在普通的 win10 版本上可以直接双击安装，就像.exe 文件一样，不过 LTSC 版本上没有 app installer 这个组件，因此也无法直接安装，需要用到如下命令：

```
Add-AppxPackage -Path .\文件名.msix
```

安装过程还是挺快的，执行命令之后几乎立即就安装好了。

然而这个命令我一年也用不到几次，显然是记不住的，于是写成一个 bat 文件存起来，以后要用时直接把.msix 文件拖到这个 bat 文件上就好了。

```
@echo off
powershell -Command "Add-AppxPackage -Path '%~1'"
echo 安装完成！按任意键退出...
pause
```

需要注意的是，保存时的编码格式不要选默认的 UTF-8，而要改为 ANSI，不然执行命令时的中文会显示为乱码。
