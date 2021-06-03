---
title: 使用Jekyll在GitHub上写博客
date: 2021-05-19
tags: github
---


## 使用Jekyll 在GitHub上写博客



* 注册一个163.com的免费邮箱（其他邮箱可自己实验，也许github对邮箱没有要求)，用来接受github发送的验证信息。

* 在Github上注册一个账户。

  * 使用注册的邮箱完成github账户的认证

  * 在Github上新建一个仓库，仓库名称为username.github.io

  * 注意留心一下仓库建立完毕后，github显示的关于操作github的git命令帮助文档。

    

* 下载并安装Windows版本的Git

  * 了解git

  * 打开git bash 命令窗口

  * 在git bash 下设置与github通讯的用户名和邮箱：

  * 在git bash 下新建一个ssh协议的密钥： ssh-keygen   -et25519   xxxxx

  * 登陆到github上，在setting 下把新产生的ssh密钥复制并保存。

  * 可以使用git 命令测试一下与github的链接是否成功。

  * 此时就可以按照github提供的git命令帮助文档实现和github仓库的通讯。

    

* 因github网络的问题，可以下载个专门的设置hosts文件的工具，有现成的很简单，在一定程度上解决网络访问问题。当然，有空的话了解一下为什么后更好。
* 熟悉了git 命令操作github仓库后，就可以开始学习github推荐的jekyll博客工具
* jekyll的安装
  * 参考官方文档的安装帮助:[Jekyll on Windows | Jekyll • Simple, blog-aware, static sites (jekyllrb.com)](https://jekyllrb.com/docs/installation/windows/)
  * 大致流程就是下载Windows版本的ruby安装包，安装ruby
  * 安装jekyll
  * 安装gem  ，gem相当于是ruby的包管理器，而jekyll就是ruby的一个应用包。关于gem ：RubyGems is a package management framework for Ruby.这是官方的描述。

```markdown
Jekyll requires the following:

Ruby version 2.4.0 or higher
RubyGems
GCC and Make
See Requirements for guides and details.

---------------------------------------------------------------

Instructions

1、Install all prerequisites.
2、Install the jekyll and bundler gems.
   `gem install jekyll bundler`
3、Create a new Jekyll site at ./myblog.
    `jekyll new myblog`
4、Change into your new directory.
     `cd myblog`
5、Build the site and make it available on a local server.
     `bundle exec jekyll serve`
6、Browse to http://localhost:4000`


```

* 使用Markdown文本编辑器Typora在本地仓库_posts目录下编辑你博客文档，记得在markdown文档的最前边填写Jekyll出路文档的元数据，格式如下：

  ```markdown
  ---
  layout: post
  title: 使用Jekyll在GitHub上写博客
  date: 2021-05-13
  Author: xian shan 
  categories: 
  tags: [github, blog]
  comments: true
  ---

如果每次书写这些数据对不方便，可保存成一个单独的markdow文件，切换到markdown源代码视图下(Ctrl+/)，复制粘贴到文档的最顶部即可。

