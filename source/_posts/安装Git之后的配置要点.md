---
title: 安装Git之后的配置要点
date: 2021-05-31
toc: true 
tag: 
  - git
---

###  在本地计算机安装Git之后，配置用户信息并添加SSH到github

为操作github仓库，需要在下载git并安装在本地计算机，具体操作有下面3个步骤

##  配置用户和邮箱信息

  ~~~
  git config --global user.name "github-username"
  git config --global user.email "username@xx.com"
  ~~~

  

##  使用ssh-keygen 生成SSH密钥对

  ~~~
  ssh-keygen  -t rsa -C "${git config.user.email"  -----
  ~~~
##  在github上保存刚刚生成的SSH。具体步骤如下：

  ```
  登录github账户，点击右上角的用户账户图标，选择弹出菜单的settting，在左侧的选项里选择SSH and GPG keys，下面的图一。最后在new sshkey界面的编辑框里粘贴ssh-keygen生成的公钥文件(.pub文件)的所有内容，最后保存，如下面图二。
  备注： clip < id_rsa.pub   这个命令可以把公钥文件的所有内容输出到剪贴板，在需要的地方粘贴即可。
  ```

  图一：

  ![image](/images/github-new-ssh.png)

  图二

 ![img](/images/ssh-key-new.png)
