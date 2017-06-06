---
layout: post
title: 在Github上搭建Jekyll博客和创建主题
---
http://yansu.org/2014/02/12/how-to-deploy-a-blog-on-github-by-jekyll.html

之前本来想展开写的，后来发现Jekyll官网的教程已经非常完善了就没有多写，所以只有这篇。 但是过了这么久，发现很多人还是不清楚怎么搭建，所以这里打算详细写一下，并且把自己对图片的解决方案以及主题的创建步骤也一并写下。

本篇主要谈如何搭建，不再讲为什么用它们。

说明：本篇用到的代码中，为了防止解析冲突，一律多了\这个来防止被误解析

## 创建一个库

在Github上新开一个库，名字叫做username.github.io，然后当别人在地址栏输入相应url的时候就可以访问进来了。

在这个库中完全可以只上传一个index.html，来讲自己要写的东西写进去，但是这样会丧失很多灵活性，所以需要Jekyll的帮助来创建自己的博客。

## 设定目录结构

把自己的库clone到本地来，建立如下目录结构：

```a
├── CNAME
├── README.md
├── _config.yml
├── _includes
│   ├── disqus.html
│   ├── footer.html
│   ├── googleanalytics.html
│   ├── header.html
│   └── navside.html
├── _layouts
│   ├── base.html
│   ├── book.html
│   ├── page.html
│   └── post.html
├── _posts
│   ├── Book
│   ├── Life
│   ├── Resource
│   ├── Technology
│   └── Tool
├── index.html
├── pages
│   ├── about.html
│   ├── archive.html
│   └── atom.xml
├── public
│   ├── css
│   ├── fonts
│   ├── img
│   ├── js
│   └── upload
└── sitemap.txt
```

这个目录结构是我自己设定的，也可以有不同的目录结构，看官网。

接下来我主要解释这里面每一个目录的功能。

### 配置文件

\_config.yml里写有整个站点的主要配置项，我的如下：

```a
permalink: /:year/:month/:day/:title.html   #博文的固定链接
paginate: 10                                #分页时每页博文数量
author:                                     #自定义常亮
  name: 闫肃
  email: yansu0711@gmail.com
  link: http://yansu.org
title: 闫肃的博客                             #自定义常量
locals:                                     #自定义常量
  tags: 标签
  about: 关于
active: 技术                                 #自定义常量
subscribe_rss: /pages/atom.xml              #订阅地址
markdown: redcarpet                         #markdown解释器
```

这里的自定义常量可以在模板中使用，以后有修改的时候就不需要跑去改代码了。尤其是对一些私人的选项，可以在这里定义。现在我的博客中出了disqus和googleanalytics外都直接在这里设定就好了。


