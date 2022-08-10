---
title: 什么才是操作系统
excerpt: 关于操作系统与测试
categories:
  - system
  - 月光之谈
comments: true
tags: 
  - system
  - notalkstateaffairs
  - test
keywords: 'notalkstateaffairs,java'
---

1. 操作系统大部分情况下是计算机软件中最底层的，因为操作系统管理硬件资源。因为人们使用操作系统就是为了征服纯硬件的裸机——没有征服裸机之前，没有软件可以顺利运行在裸机上。
1. 操作系统有控制程序运行的能力。倘若没有操作系统的控制，一台机器上多个程序难道还要自己竞争去进行吗？程序还要想自己要怎么使用内存和硬盘吗？操作系统控制程序运行不仅需要做到高效，还需要做到安全——保证各个程序之间不会互相干扰对方，最重要的是不要把操作系统破坏了。
1. 操作系统需要人机交互——哪怕是最原始的计算机也是需要人机交互，虽然方式可能要比现在落后得多，没有人机交互的计算机跟石头没什么两样
1. 操作系统往往设置有系统调用，供应用软件使用。既然操作系统是管理硬件资源的，而应用软件也会经常用到硬件资源。一方面为了方便，另一方面为了安全，应用软件就需要跟操作系统申请资源来用，这些申请就设计成为操作系统的系统调用，也就是操作系统对上层的接口

![](https://pic2.zhimg.com/80/v2-5ee5fc9da8edbe5bfd72ebb1f9bc13d1_720w.jpg)

比如 `Windows` 虽唱衰声一片，但是人家有他自己的 `RT` : `WinRT`。

曾经，所谓 `WinMe` 之类，只是在 `DOS` 上的应用而已，如今，`WinServer`，作为服务器的 `OS`，又如此伟大

所以，我个人认为，操作系统，不同于 `UI`，应该有自己的运行时与 `API`，严谨且正确的文档，而不单单只是几个系统应用、系统控件的差距，就可以证明是不同的操作系统。

其必须要有自己的运行时，自己的内核代码，否则正如 `Linux` 与 `Ubuntu` 的关系一样，我们只是称后者为前者的一个 **发行版**。

谢谢。