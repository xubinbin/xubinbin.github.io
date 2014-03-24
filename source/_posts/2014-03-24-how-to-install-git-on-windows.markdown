---
layout: post
title: "在Windows下安装Git的详细步骤及说明"
date: 2014-03-24 16:44:52 +0800
comments: true
categories: 
---
　　Git是一个免费的、开源的版本控制软件。在Windows下安装Git，一般为msysgit，官方下载地址为：
　　http://code.google.com/p/msysgit/downloads/list

下载：

在官方网站，排在第一个的即为最新版本，点击下载。
![Alt Git Download](http://xubinbin.qiniudn.com/git%E5%AE%98%E6%96%B9%E4%B8%8B%E8%BD%BD%E6%88%AA%E5%9B%BE.jpg
 "下载Git")
<!--more-->
安装：

欢迎界面，点击Next；
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B1.jpg
 "安装Git步骤1")

同意条款，点击Next；
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B2.jpg
 "安装Git步骤２")

选择程序安装路径，点击Next（比如我的应用程序都是装在E:\Program Files下，我就直接修改盘符为E）；
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B3.jpg
 "安装Git步骤３")

对照下图勾选安装选项，点击Next；
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B4-1.jpg
 "安装Git步骤４")

在开始菜单创建文件夹（勾选左下角方框可跳过创建，不推荐），点击Next；
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B5.jpg
 "安装Git步骤５")

“Adjusting your PATH environment”选项：在Windows下，应选择第一个选项 Use Git Bash only，点击Next；

TIPS:
1. PATH是操作系统用于查找来自命令行或终端窗口的必需可执行文件的系统变量。
2. Cygwin是用于在Windows操作系统上建立一个类似Unix的环境，执行Unix的指令及众多应用程序的模拟器。
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B6-1.jpg
 "安装Git步骤６")

“Configuring the line ending conversions”选项：在Windows下，应选择第一个选项 Checkout Windows-style, commit Unix-style line endings，点击Next；

TIPS:
1. 因为Git版本控管早期是为了维护庞大的Linux kernel而设计而成的，所以绝大部分的使用环境都是Linux平台。在Linux平台下，文字档案的预设断行符号为LF字元( \n ) ( 0x0A )。而在Windows环境下，文字档案的预设断行符号却是CRLF字元 ( \r\n ) ( 0x0D 0x0A )，比Linux多一个字元。
2. 第一个选项会让Git指令在执行的时候，自动转换断行符号。简单来说，就是“当执行git add命令将工作目录中的档案加入版本库时，文档中出现的CRLF断行字元会自动被转换成LF字元。同样的，当执行git checkout指令，取出版本库中的档案到工作目录时，文档中的LF字元也将会被自动转换成CRLF字元。
3. 如果你忘记在安装时设定的是第几个选项，可以执行git config core.autocrlf指令查询，若返回true，则表示选择的是第一个选项。
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B7.jpg
 "安装Git步骤７")

程序开始安装...
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B8.jpg
 "安装Git步骤８")

取消勾选，可不打开帮助文件。点击Finish，完成安装。
　　![Alt Git Install](http://xubinbin.qiniudn.com/git%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B9.jpg
 "安装Git步骤９")



 本文参考了以下资源：

[1] [Git在Windows平台处理断行字元（CRLF）的注意事项](http://blog.miniasp.com/post/2013/09/15/Git-for-Windows-Line-Ending-Conversion-Notes.aspx)

[2] [How to install Git on Windows with msysgit](http://buildamodule.com/video/change-management-and-version-control-installing-git-and-working-on-the-command-line-how-to-install-git-on-windows-with-mysysgit#viewing)