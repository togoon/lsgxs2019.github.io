---
title: 批处理设置IE浏览器可信任站点和ActiveX项目
date: 2021-07-21 20:09:00
tags: 单位系统维护
categories: 系统维护
---

#### 使用批处理设置IE浏览器安全站点及ActiveX各项参数



* 首先重置浏览器。

* 进入业务系统，下载插件，安装高拍仪的驱动。一般会提示带有三个项目（安装、更新、卸载）的安装界面。此时选择卸载。卸载完成后，再安装一次高拍仪的驱动即可

* 运行批处理设置IE的各项参数

  <!--more-->

~~~html
REM 添加信任站点ip
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap\Ranges\Range10" /v ":Range" /t REG_SZ /d   x.y.z.1  /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap\Ranges\Range10" /v "http" /t REG_DWORD /d 2 /f


 

REM 添加信任站点域名
rem reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap\Domains\xxx.com" /v "http" /t REG_DWORD /d "2" /f
rem reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap\Domains\xxx.cn" /v "http" /t REG_DWORD /d "2" /f

REM ActiveX的注册表项
REM 值         设置 
REM ------------------------------ 
REM 0        我的电脑 
REM 1        本地 Intranet 区域 
REM 2        受信任的站点区域 
REM 3        Internet 区域 
REM 4        受限制的站点区域 
 
REM 1001     下载已签名的 ActiveX 控件 
REM 1004     下载未签名的 ActiveX 控件 
REM 1200     运行 ActiveX 控件和插件 
REM 1201     对没有标记为安全的 ActiveX 控件进行初始化和脚本运行 
REM 1405     对标记为可安全执行脚本的 ActiveX 控件执行脚本 
REM 2201     ActiveX 控件自动提示

reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2" /v "1001" /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2" /v "1004" /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2" /v "1200" /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2" /v "1201" /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2" /v "1405" /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2" /v "2201" /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\2\ /v "120B" /t REG_DWORD /d 0 /f

REM 弹出窗口阻止程序的注册表项 
REM WshShell.RegWrite("HKCU\\Software\\Microsoft\\Internet Explorer\\New Windows\\PopupMgr","no");
reg add "HKCU\Software\Microsoft\Internet Explorer\New Windows" /v "PopupMgr" /t REG_SZ /d no /f
~~~

* 因IE浏览器只能受理少数几笔业务就会卡机，更换为360浏览器可以正常受理，如果出现浏览器异常错误信息的话，设置360浏览器的退出清除项目，及时清理浏览记录，释放缓存。
