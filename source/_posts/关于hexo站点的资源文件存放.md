---
title: 关于hexo站点的资源文件存放
date: 2021-05-30
toc: true 
---

## Asset Folder in Hexo blog 



### Global Asset Folder

Assets are non-post files in the `source` folder, such as images, CSS or JavaScript files. For instance, If you are only going to have a few images in the Hexo project, then the easiest way is to keep them in a `source/images` directory. Then, you can access them using something like `![](/images/image.jpg)`.

可以把markdown撰写post时引用的图片文件保存在hexo项目的source/images目录下，在markdown编辑器里引用图片的格式为![img](/images/image-name.jpg or .png)



###  Post Asset Folder

<iframe src="https://www.youtube.com/embed/feIDVQ2tz0o" frameborder="0" loading="lazy" allowfullscreen="" style="box-sizing: inherit; margin: 1em 0px; padding: 0px; border: 0px; outline: 0px; font-weight: inherit; font-style: inherit; font-family: inherit; font-size: 15px; vertical-align: baseline;"></iframe>

For users who expect to regularly serve images and/or other assets, and for those who prefer to separate their assets on a post-per-post basis, Hexo also provides a more organized way to manage assets. This slightly more involved, but very convenient approach to asset management can be turned on by setting the `post_asset_folder` setting in `_config.yml` to true.

```yaml
_config.ymlpost_asset_folder: true
```

With asset folder management enabled, Hexo will create a folder every time you make a new post with the `hexo new [layout] <title>` command. This asset folder will have the same name as the markdown file associated with the post. Place all assets related to your post into the associated folder, and you will be able to reference them using a relative path, making for an easier and more convenient workflow.

