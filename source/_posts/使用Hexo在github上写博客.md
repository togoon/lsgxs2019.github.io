---
title: 使用Hexo在github上写博客
date: 2021-05-19
tags:  Hexo
---

## 使用Hexo在github上写博客

* 了解Hexo

> Hexo是一个简洁而强大的博客框架。使用markdown编辑器写文章，Hexo把这些markdown文章生成静态的拥有漂亮渲染效果的网页文件。

* Hexo博客环境的搭建

  * 安装Git

  * 安装Node.js

  * 安装Hexo(推荐在git的bash命令 窗口下安装)

    * npm install hexo  -g hexo-cli

      

* 使用Hexo建立博客站点项目

  * hexo init   foldername

  * cd   foldername

  * npm install

    

 博客站点项目生成后，目录结构如下图：

![img](https://www.xianshansky.top/img/hexo/configfile.jpg)

* 下载并应用主题（Themes）

  ```
  $ cd your-hexo-site
  $ git clone https://github.com/iissnan/hexo-theme-next themes/next
  ```

  themes目录下的next目录，就是下载的next主题，还需要在设置_config.yml文件应用next主题：

  ```bash
  # Extensions
  ## Plugins: https://hexo.io/plugins/
  ## Themes: https://hexo.io/themes/
  theme: next
  
  # Deployment
  ## Docs: https://hexo.io/docs/deployment.html
  deploy:
  type: git
  repo: git@github.com:username/username.github.io.git
  branch: master
  ```

  

* 编辑hexo项目的配置文件_config.yml

* 使用Typora建立你的博客文档，保存在项目的/sourece/_posts目录下

* 使用Hexo的一键部署功能把整个项目上传到github pages上

  * install hexo-deployer-gt

    * ```
      npm install hexo-deployer-git --save
      ```

  * add the following configuration to _config.yml

    ```bash
    deploy:
      type: git
      repo: <repository url> # https://github.com/username/username.github.io
      branch: [branch]
      message: [message]
    ```
  
* hexo clean  （如果修改了已经发布的文档，需要使用hexo clean来清理一下，会自动删除public目录和db.json文件） 
  
* hexo generate   or hexo g 
  
*  hexo deploy     or hexo d      hexo g -d   （也可以把生成和发布组合起来一步完成：hexo g -d   g  和d  没有先后顺序，不过最后一个参数前要加段横线）
  
*  在发布到username.github.io仓库之后，CNAME文件被删除了，要在username.github.io仓库的根目录下新建一个CNAME文件，把解析的内容填写好提交就可以在浏览器看到最新的内容。也可以在hexo  clean & hexo generate 之后，使用记事本在public目录下新建一个CNAME文件，使用hexo d之后，会把当前public目录的内容发布到username.github.io
  
* Check the webpage at username.github.io

​       