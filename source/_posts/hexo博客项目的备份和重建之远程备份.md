---
title: hexo博客项目的备份和重建之远程备份
date: 2021-05-24
author: xian shan
img: /images/logo.svg
top: true
cover: true
coverImg: /images/logo.svg
toc: true
mathjax: false
summary: 了解hexo项目的目录结构,使用hexo deploy发布静态网页,同时使用git命令备份项目文件到远程的github仓库分支，了解hexo项目的目录结构,使用hexo deploy发布静态网页,同时使用git命令备份项目文件到远程的github仓库分支
categories: hexo
tags:
  - hexo
  - git
---

####  认识hexo项目的目录结构

使用hexo init之后，hexo会在你指定的目录下创建项目所需的目录和文件,如下图所示

```tiddlywiki
.github     ----
node_modules----项目依赖的包文件
scaffolds   ----模版文件
soruce      ----保存用户文档
themes      ----主题包目录
.gitignore  ---- 指定的不纳入git管理的内容
_config.landscape.yml----
_config.yml ----项目配置文件
package.json----
package-lock.json
```

在初始化hexo项目目录之后，基本的博客框架建立，就可以开始使用markdown编辑器书写文档，保存在source\_posts目录下。

文档编辑完成后，就可以使用hexo generate 来生成静态的网页文件，所有生成的文件都保存在public目录下。这段英文来自hexo官方文档的描述:

> All generated files are saved in the `public` folder. You can copy them to wherever you like。

此时hexo博客项目的目录下又多了public目录和db.json。db.json是以json格式的文件来保存你的博客文档的元数据。
```tiddlywiki
.github     ----
node_modules----项目依赖的包文件
public      ----hexo generate 生成的所有静态网页文件及资源文件
scaffolds   ----模版文件
soruce      ----保存用户文档
themes      ----主题包目录
.gitignore  ---- 指定的不纳入git管理的内容
_config.landscape.yml----
_config.yml ----项目配置文件
package.json----
package-lock.json
db.json
```

#### 在本地使用发布静态网页和备份项目文件的命令

第一步、发布文档

```bash
hexo clean 
hexo g
hexo d
```

  第二步、备份项目文件到github仓库的指定分支

```bash
使用gi命令上传到github单独的仓库或者分支，这个可以作为hexo博客项目的备份方法。
git  add .
git commit-m "push hexo project fiels"
git push origin main:hexo
```

#### 通过git命令把hexo项目保存在github的username.github.io仓库

在本地把hexo项目纳入git管理

```bash
在本地新建一个目录hexo-source，用来保存hexo项目
cd hexo-source
git init 
git checkout --orphan source 
```

把博客项目复制到hexo-source目录下

```markdown
 把hexo博客项目根目录下的所有内容复制到hexo-source目录
 在.gitignore文件中仅保留下面三项内容（从hexo init 、hexo generate、hexo deploy这三个步骤来看，只有这三项是通过项目框架动态生成的，可以删除).从自己的实践来看，.gitignore文件是为git命令而设定的。比如，如果按照该文件默认的设置，是包含node_moudles项目的，也就是在git add & git commit -m "xx" &git push 时，不会上传node_moudles的，好处是节省带宽，但是如果上传node_moudles的话，再次git clone博客项目时，不必再次运行 npm install(也许你已经忘记了)，就可以直接开始写markdown文档，然后hexo g -d 就可以完成所有流程。
     public/
     .deploy*/
     db.json
     
```
把博客项目推送到github仓库

  ```bash
   git add .
   git commit -m "add hexo blog project source to githut repo branch "
   git remote add origin https://github.com/lsgxs2019/lsgxs2019.github.io
   git push origin source:source   ---- 推送hexo项目到username.github.io的source分支
   设定username.github.io仓库的默认分支为source（我这里的名称为source）
  ```

在本地恢复博客项目

```tiddlywiki
如果项目文件出错的话，就可以直接在本地使用git clone 来下载username.github.io仓库到本地，实现快速恢复，提高工作效率。
```

具体执行过程见下面的图片

![img](/images/hexo/create-empty-branch-to-github.jpg)

