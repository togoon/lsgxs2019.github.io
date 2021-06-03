---
title: 关于git与github通讯的Https协议和SSH协议
date: 2021-05-30
tag: 
    -SSH
    -Https 
---

## git与github通讯的Https协议和SSH协议

在安装Git后，需要使用git命令与github仓库通讯，一般由两种协议实现与git与github仓库的通讯

* ## https

  如果刚刚接触git和github，使用https协议与github通讯比较容易上手，顺利实现各种git命令的操作。一般复制仓库的本地的git命令如下

  ```bash
  git clone https://github.com/username.gitbub.io.git 
  git clone 命令是多个git命令的封装，相当在本地新建立的username.github.io目录，再执行git init 纳入.git管理,自动建立一个master分支（git checkout -b master），自动添加远程连接git remote add origin https://github.com/username.gitbub.io.git，再 git fetch下载数据
  ```

  只是在每次都要输入用户名和邮箱，有点不方便，需要再使用git config  --global  user.name  "git用户名" 和git config --global  user.email "注册git时的邮箱"

* ## SSH

  SSH的全称时Secure Shell,通过一对加密的密钥来实现客户端和服务器的通讯。在 Git Bash 命令行窗口下，使用以下命令来生成SSH密钥

  ```bash
  1.ssh-keygen  -t rsa  -C "username.com--这里是密钥的注释，一般使用邮箱可说明它的用途"
  这里的-t rsa 参数知名密钥类型为rsa，-C 为注释。也可以再加上-f filename来指定密钥的文件名称。
  在安装git之后，使用这个命令可在默认的路径下生成id_rsa.pub和id_rsa这两个公钥和私钥文件，一般要查询他的路劲，可在git bash 命令行下输入下面的命令：
  cd ~/.ssh
  ls -al 
  2.如果已经生成过密钥的话，就会显示这两个文件，在ssh-keygen命令中不带-f filename 参数的话，默认的文件名是id_rsa 和id_rsa.pub。
  3.在git bash命令窗口下使用clip < id_rsa.pub，可以把文件的内容复制到剪贴板上，登录到github，在网站的setting下打开SSH及GPG Keys选项，titile随便自己一个，把剪贴板的内容粘贴在ssh-key里，保存即可，以后使用git 操作github仓库时就可以使用git@github.com:username/username.github.io.git的格式了，这个据说时传输数据的效率比https更高一些。
  4.如果后来又重新生成了一对密钥文件，并且把公钥的内容添加在github上之后，就要把这对密钥对应的私钥覆盖到~/.ssh目录下，这个是安装git时默认的路径，如果想修改git 使用的密钥文件的话，就要修改环境变量，不想麻烦的话，就把新生成的密钥文件改名覆盖原来的密钥对文件即可。
  ```
  
  
  
  

