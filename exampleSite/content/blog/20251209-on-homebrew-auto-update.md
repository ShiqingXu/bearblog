+++
title = "关于Homebrew Auto Update"
date = "2025-12-09T21:05:37+08:00"
images = ["https://img.14says.xyz/2025/12/1765286036-20251209-on-homebrew-auto-update-banner.webp"]
tags = ["software", "折腾",]

+++

![20251209-on-homebrew-auto-update-banner](https://img.14says.xyz/2025/12/1765286036-20251209-on-homebrew-auto-update-banner.webp)

我并不经常使用 homebrew，但是每次使用都会遇到一个令人头痛的问题，就是当我要通过 homebrew 安装一个软件时，它首先会试图自动更新。而在世界上有些地区，homebrew 的更新是非常难的。很不幸，我恰好就位于这样的地区。

不过我之前并没有想过去解决这个问题，正如前面所说的那样，我并不经常使用 homebrew，并且也没意识到这是一个在某些地区独有的问题。

直到上周末我要安装一款只能通过 homebrew 安装的软件，第一天晚上尝试了几次均以失败告终，因为每次的自动更新都会在等待很长时间以后失败。第二天再度尝试，依然失败，这时候我才想起来去研究一下怎么一劳永逸地解决这个问题。

查了一下，方案异常简单，与Linux 的软件源更新一个逻辑，那就是换成国内的替代软件源。

## 打开 shell 配置

我的macOS使用的是默认zsh，运行 `open -e ~/.zshrc`可打开配置文件，如果没有的话需要先创建这个配置文件，命令为 `touch ~/.zshrc`

## 添加国内替代镜像源

打开配置文件之后，在其中添加国内比较流行的清华大学镜像源，比较稳定，速度也快。

```jsx
# Homebrew 核心程序镜像
export HOMEBREW_BREW_GIT_REMOTE="<https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git>"

# Homebrew API 镜像 (Homebrew 4.0+ 关键配置)
export HOMEBREW_API_DOMAIN="<https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/api>"

# Homebrew 二进制预编译包镜像 (下载软件本身的速度)
export HOMEBREW_BOTTLE_DOMAIN="<https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles>"
```

## 保存并生效

完成上一步之后保存文件，运行 `source ~/.zshrc` 使其生效。完成之后试了一下 `brew update`，果然速度飞快了。

## 临时绕过的方法

上面的方法是永久解决更新速度慢甚至失败的问题，有时候如果实在着急，也可以临时绕过自动更新，方法是在需要运行的目标命令前加上 `HOMEBREW_NO_AUTO_UPDATE=1`，这样就会直接执行后面的命令，而不会触发自动更新了。

设置完之后我运行了一下 `brew upgrade`，发现已经有十几个软件版本落后了，可见我真的不怎么用。
