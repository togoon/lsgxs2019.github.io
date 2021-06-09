---
title: HowtoUseHexo
date: 2021-05-18 19:05:59
tags:  hexo
---

* install node.js 和git
* install hexo  （ git bash）

* hexo init

```bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```

*  Configuration   _config.yml

* write post

  ```bash
  hexo new  <title>
  ```

* generate

  ```bash
  hexo generat or hexo g
  ```

* server 

  ```bash
  hexo server
  ```

* deploy

  ```bash
  本地浏览 localhost:4000
  部署到github.com :hexo deploy  or hexo d
   
  ```

  重新修改post之后

  ```bash
  hexo clean  （删除db.json数据库和由generate生成的保存html文件的public目录）
  hexo generate （重新把source目录下的md文档生成每个文件夹下的index.html文件，这些文件夹都是以年月日建立的目录树，所有要发布的内容保存在public目录下）
  hexo server 
  localhost:4000   
  hexo deploy  （一般要执行hexo deploy 或者hexo d,hexo deploye时， 是先清空.deploy_git目录，然后从public目录所有内容复制到到.deploy_git目录，按照_config.yml里设置的deploye参数push到远程仓库。如果自己手动在git bash 命令窗口下使用git 命令push到远程的仓库，需要推送的是public目录，而不是项目目录。如果没有完整的项目文件，可以直接使用git clone把远程仓库的所有内容clone到本地，修改之后在再直接push到远程，不过一不推荐这个方式，容易出错，只是通过这种方式熟悉hexo的工作流程。hexo必须把markdown文件在本地转换成html再上传到github，而github对jekyll的支持，可以直接push本地的markdown文件到github仓库，由github提供的服务把markdown转换为html。
  
  ```

  这里的图片引用使用域名+站点目录的形式

  ```markdown
  ![img](https://customedns\images\xxx.jpg)
  想在markdown文档中引用图片，可以把图片保存在站点根目录的images目录下。需要在运行hexo generate命令之后，把图片复制到生成的public\images目录下，然后由hexo deply把public目录复制到.deploy_git目录，git上传到到username.github.io站点根目录下
  ```

  

  ![img](https://www.xianshansky.top\images\after-hexo-deploy-repo-local.jpg)

![img](https://www.xianshansky.top\images\after-hexo-deploy-repo.jpg)

![img](https://www.xianshansky.top\images\hexo-deploy.jpg)

## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)