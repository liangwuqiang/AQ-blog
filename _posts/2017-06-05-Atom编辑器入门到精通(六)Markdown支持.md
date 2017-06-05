---
layout: post
title: Atom编辑器入门到精通(六)Markdown支持
---
原文：http://blog.csdn.net/u010494080/article/details/52491678

尽管我们使用Atom主要是为了编写代码,不过Atom还支持编辑很多其他格式的文件. 比如Markdown和Asciidoc. 这一章中我们主要学习如何快速方便地编辑Markdown文件.

另外在写这篇博文的时候我又换回Linux了, 因此以后文章里提到的快捷键和操作方式都将以Linux为标准.

## 拼写检查

当我们编辑文本时(包括纯文本文档,Markdown,Git提交信息等), Atom会自动尝试做拼写检查.

如果某个词拼写错误, Atom会将其高亮.

在这个时候你可以使用Ctrl+Shift+;或右键菜单(或命令面板)中的Correct Spelling来弹出一个包含修改参考项的菜单来进行拼写错误的修改.

![Spell  Check](..\images\Atom\spellcheck.png)

此功能是通过插件spell-check来实现的, 因此你可以在插件设置窗口中对此功能进行一些设置.

## 预览

在进行Markdown文档的编辑时, 我们经常想要看一看编辑的效果. Atom默认就支持这一功能.

我们只需要在编辑md文件时使用Ctrl+Shift+M, 就能显示一个预览窗口, 方便我们随时查看md编辑的效果. 并且这个预览窗口还能随着我们的编辑自动刷新预览的内容和效果.

![Spell  Check](..\images\Atom\preview.png)

最后, 你还能使用命令Markdown Preview Copy HTML来将预览的效果以HTML的格式复制到系统的剪贴板上.

## Snippets(代码片段)

Atom中内置了多个Snippets来方便Markdown文档的编辑.比如img(插入图片), table(插入表格), b(插入粗体), i(插入斜体), code(插入代码)等.

关于Snippets的详细使用方法请参考本系列文章的第四章Atom使用进阶.
