---
title: 把Hexo生成的静态网页部署到coding上
date: 2021-06-08
tags:  coding
description: 因为github的网速问题，可以尝试把hexo生成的静态博客文件发布到国内的coding上。
---

## 把Hexo生成的静态网页部署到coding上

因为github的网速问题，可以尝试把hexo生成的静态博客文件发布到coding上。
* 首先注册coding账号([CODING - 一站式软件研发管理平台](https://coding.net/))，并绑定腾讯云（需要实名认证）
* 新建5人以下团队的项目
* 新建代码仓库(选择devops)，可以选择添加readme文件
* 点击代码仓库中，在左下角显示项目设置，再选择功能开关，如果不熟悉，可以打开所有功能开关，持续集成和持续部署要选择。
* 在本地的git bash 命令窗口下，使用clip < id_ed25519.pub ，把公钥的内容输出到剪贴板，在coding的个人账户设置里，添加公钥内容并保存。使用ssh -T  git@coding.net  测试ssh协议链接。
*  编辑hexo博客项目根目录下的_config.yml文件，把deployer段的内容修改下面的内容：

```yaml
deploy:
  type: git
  repo: git@e.coding.net:username/myblog/hexoblog.git
  branch: master  

```

* hexo g -d   发布到coding腾讯云空间
* 部署成功后，设置自定义以域名

###  部署在coding的静态网站的收费标准

* 有6个月的免费试用期，后期应该是要收取费用的，具体可以查看coding 官方的资费明细

### 自动部署

也可以实现自动部署博客到coding