---
title: mac升级10.15(catalina)后virtualbox无法启动和异常退出问题解决
date: 2019-10-12 11:12:00
categories:
- 其他
tags:
- mac
---

mac升级catalina之后，遇到了virtualbox无法启动或启动后异常退出问题。垃圾的mac，苹果在
作死和封闭的道路上越走越远。以后再说“苹果重视用户体验”之前请确认这句话是过了大脑的。

* TOC
{:toc}


# 问题1：virtualbox无法启动
虚拟机完全不能启动，通常原因是catalina系统严格的权限限制导致的，需要为virtualbox添加
完全磁盘访问权限  
![添加完全磁盘访问权限](/assets/images/my_img/mac升级10.15后virtualbox无法启动和异常退出问题解决/添加完全磁盘访问权限.png)  

# 问题2：鼠标移出虚拟机窗口时virtualbox异常退出
虚拟机能够正常启动，但是鼠标移出虚拟机窗口时，虚拟机窗口发生crash，异常退出，
具体讨论可以参见[virtual box crashs](https://discussions.apple.com/thread/250716588),
解决方式为在终端执行以下命令行：
```sh
VBoxManage setextradata global GUI/HidLedsSync 0
```
