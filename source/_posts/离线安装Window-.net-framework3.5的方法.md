---
title: 离线安装Window .net framework3.5的方法
date: 2021-06-09
tags:
  - windows
  - net framework3.5
toc: true 
banner: /images/test.png
---

##  Windows10下安装dot net framework3.5的方法

#### 在线安装
有网络的情况下，dot Net Framework3.5是很简单，在win10下控制面板的程序功能下，点击开启或者关闭windows功能，直接选择开启或者关闭dot net framework3.5即可。如果没有网络的情况，可以使用下面两种方法之一安装dot net framework.

<!--more-->

#### 离线安装

* 从windows官网下载 dot net framework3.5离线安装包和语言包。
  * 完整软件包(231M)下载地址：[Download Microsoft .NET Framework 3.5 Service Pack 1（完整软件包） from Official Microsoft Download Center](https://www.microsoft.com/zh-cn/download/details.aspx?id=25150)
  * 语言安装包下载地址：[Download Microsoft .NET Framework 3.5 SP1 语言包 from Official Microsoft Download Center](https://www.microsoft.com/zh-cn/download/confirmation.aspx?id=21891)

* 解压dotnetfx35.exe，把x64系统的语言包复制到.\dotnetfx35\wcu\dotNetFramework\dotNetFX35\x64目录下面
* 直接运行.\dotnetfx35\wcu\dotNetFramework\dotNetFx35setup.exe即可离线安装dot net framework3.5

#### 使用Windows安装介质启用Windows10的dot net framework 3.5

* 使用管理员用户权限（以管理员身份运行）打开命令提示符。

* 若要从位于“D:”驱动器上的安装介质安装 .NET Framework 3.5，请使用以下命令 ：

  ```html
  DISM /Online /Enable-Feature /FeatureName:NetFx3 /All /LimitAccess /Source:d:\sources\sxs
  ```

  使用“/All”启用指定功能的所有父功能 。

  使用“/LimitAccess”阻止 DISM 与 Windows 更新/WSUS 联系 。

  使用“/Source”指定还原功能所需的文件的位置 。

