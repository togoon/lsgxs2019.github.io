---
title: html学习笔记之html文件结构
date: 2021-06-20 06:52:57
tags: html
categories: web
description: 从最简单的html文件说起，掌握基本的html文件框架结构
cover:
thumbnail:
---

## HTML语言简介

html语言是网页内容的基础，以标签式的结构和内容书写Html文件，由浏览器解释这些格式标签后，将html文件的内容渲染后在浏览器呈现。现在的网页技术涉及到html、css、javascript。html负责html文件的格式和内容，css渲染网页的样式，javascript用来在html中引入编程逻辑，生成更加丰富的交互式网页。

<!--more-->

## 最简单的html文件结构

```html
<!DOCTYPE html>
<html lang="zh-CN" >

      <head>
          <meta charset="utf-8">
          <title>hello html</title>
      </head>
        
      <body>
         <p>
             这是html文件最基础的结构。最外层的是`<html>`标签对，下面是`<head>`对和'<p>'标签对，是'<html>'的子标签，这两个标签是并列关系。
             通过这样的结构，形成了树状的结构，这棵树可大可小。
             同时，每个标签包含多种属性值，以键值对的形式来书写。那是不是有点像C语言的结构体呢，定义一个结构体，然后以键值对的形式来描述各种属性
         
         </p>
         <p>
             虽然这些书写内容以一定的格式呈现，这是为了可读性而规定的。                     
         </p>

      </body>

</html>


```

## 在浏览器中打开html文件

​    使用最简单的windows记事本来编辑上面的内容，保存为html文件，使用浏览器打开后查看效果，感受一下结构、内容的呈现。



