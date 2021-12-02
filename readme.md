#### 仓库分支布局说明



* hexo-next 和hexo-matery 两个项目的备忘
  * 都是基于hexo的博客项目文件，只是两个风格不同的两个主题，一个简洁明快，一个丰富多彩。
  * 经过设置，可以使用两种方法快速发布，在本地使用hexo g -d 。也可以使用git push 到对应的源文件分支，自动执行actions部署。



* source
   * 存放hexo-icarus或者hexo-matery项目的源文件，在.github\workflow目录下有.yml文件，执行git push到souce分支时，会执行actions自动部署到master分支

* master
   * 存放hexo-matery项目生成的静态网站文件
* hexo-next-source
   * 存放hexo-next项目的源文件，在.github\workflow目录下有.yml文件，执行git push到souce分支时，会执行actions自动部署到gh-pages分支
* gh-pages
   * 存放hexo-next项目生成的静态网站文件

-----------------------------------------------------------------------------------------
