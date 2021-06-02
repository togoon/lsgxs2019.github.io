---
title: git操作git仓库命令入门
date: 2021-05-28
tag: git 
categories: git
---

* 新建一个目录 branch_demo
* cd branch_demo

* git init 
* git status 
* git checkout -b branch-name
* echo "git branch start" > readme.md
* git add .
* git commit -m "git branch start"
* git push -u origin    ----新建分支第一次推送到远程时，需要-u参数指明上游，或者使用--set-upstream,以后再推送就不需要-u参数了

* 主要看看初始化仓库之后，是不是必须有一个master分支，要显式的改名为main 
* 
