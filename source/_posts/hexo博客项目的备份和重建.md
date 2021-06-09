---
title: hexo博客项目的备份和重建
date: 2021-05-24
tag: how-to-use-hexo
---

## hexo博客项目的备份和重建之本地备份



* 如果需要重建hexo博客项目，只需要保存你的文档目录source、你的博客主题目录themes、scaffolds目录、配置文件_config.yml。
* 最好把远程仓库重新clone到本地的备份目录，可能里面会有你自定义的目录，比如images保存的各种展示图片(如果使用第三方图床就不必保存)。
* 开始重建hexo博客项目
  * hexo init 
  * npm install
  * 把前面备份的source、themes目录和_config.yml复制到新建立的hexo项目目录下。
  * hexo g
  * hexo server  
  * localhost:4000在本地查看
  * 正常显示后发布到远程的github仓库: hexo d 
    * 如果发布时出现ERROR Deployer not found: git 的错误提示信息，就再把hexo 一键发布包安装一下：npm install hexo-deployer-git  --save,然后再执行hexo d即可成功发布到github远程仓库，记得在仓库的根目录下新建CANME文件。

