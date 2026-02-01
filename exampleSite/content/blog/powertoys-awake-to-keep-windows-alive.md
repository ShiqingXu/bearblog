---
title: 用 PowerToys Awake 保持屏幕唤醒
date: 2025-09-18 08:19:01
tags: [software]
---

偶尔会有同时开着两台 win 电脑，主要使用其中一台，但需要保持另一台屏幕常亮的需求。不知为何这台电脑系统的电源计划里设置超长的屏幕关闭时长会无效，总会在无操作十分钟左右就自动关闭屏幕，需要用第三方工具来解决。



能实现这个需求的工具应该不少，首先想到的是微软的 PowerToys 里带有一个叫做 Awake 的功能。PowerToys以前用过一阵，功能丰富而强大，不过用了一阵就不用了，主要原因是公司的安全软件对其有一些拦截。而且对于我使用频率最高的启动器功能来说，有其它更好用的工具。

重新下载了 PowerToys，打开 Awake 功能。

 PowerToys 官网上对于 Awake 的几种模式的介绍：

| Setting                            | Description                                                  |
| :--------------------------------- | :----------------------------------------------------------- |
| Keep using the selected power plan | The computer power state is unaffected. PowerToys Awake runs in the background but does not request any custom power behaviors. |
| Keep awake indefinitely            | The computer stays awake indefinitely until you explicitly put the machine to sleep or close/disable the application. |
| Keep awake for a time interval     | Keep machine awake for a predefined limited time. After the time period elapses, PowerToys Awake returns to the disable state. |
| Keep awake until expiration        | Keep machine awake until a defined date and time is hit.     |

Awake 有个保持屏幕唤醒的选项，如果不勾选这个选项，屏幕依然会在一段时间不操作电脑后熄灭，尽管电脑被保持唤醒。但如果勾选了，则主动锁屏之后屏幕依然会保持常亮。

![](https://img.14says.xyz/2025/09/1758155354-PowerToys-Awake-keep-screen-alive.png)

而我的诉求是如果屏幕开着，就一直保持屏幕常亮，但当我主动锁屏后，屏幕会在一定时间后熄灭。所以并不能完全满足我的诉求。

不过也凑合能用。

能保持唤醒还有一个好处。之前我去会议室开会，通常会保持笔记本盖子打开的状态带过去，因为盒上盖子之后重新打开需要很长时间才能唤醒，唤醒后还有可能卡住，比较耽误事情。

公司给我配发的这台电脑过于老旧了，而且电源管理里面设置的盒上盖子不采取任何动作也无济于事。而有了 Awake，就可以自如盒上盖子不用担心到了会议室电脑醒不过来。

在当前这种几乎不需要出差、无需考虑笔记本续航和便携性的情况下，盒上盖子重新打开不需要等待唤醒，差不多是唯一想念 mac 的场景了。

