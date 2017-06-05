---
layout: post
title: Atom编辑器入门到精通(八) Markdown支持 (下)
---
原文：http://blog.csdn.net/u010494080/article/details/53562939

在上一章中我们了解了原生Atom对Markdown的支持, 这一讲我们一起学习如何使用更多的插件让Atom更好地支持Markdown文件.

## Markdown-Writer

如果你跟我一样, 使用Markdown格式来写博客, 那你一定也需要Markdown-Writer插件, 它能让更方便地管理和编辑Markdown文件.

先来几张官方的GIF感受一下它的功能吧

![newblog](..\images\Atom\newblog.gif)

创建新文章

![insertimg ](..\images\Atom\insertimg.gif)

插入图片

![insertlink ](..\images\Atom\insertlink.gif)

插入链接

![removelink ](..\images\Atom\removelink.gif)

移除链接

### 安装

```a
apm install markdown-writer
```

### 配置

我们可以在Atom的设置窗口->Packages->markdown-writer->Settings里来设置, 或者在上篇文章中介绍的config.cson中配置.

在siteLocalDir设置为博客根目录, 如果为空, 将会使用Atom的当前目录.

fileExtension改为.md

其他配置可以使用默认配置

如果我们同时编辑了几个博客, 可以将上述配置写在一个名为_mdwriter.cson的文件里, 并置于博客的根目录下, 这样就能在博客之间使用不同的配置了. 还有一个简单的方法是在打开博客项目后Ctrl+Shift+P执行命令Markdown Writer: Create Project Configs. 注意在修改配置以后需要执行命令Window: Reload来重新读取配置.

我的config.cson相关配置:

```a
"*":
  "markdown-writer":
    fileExtension: ".md"
    siteLocalDir: "/home/peter/src/peterho.github.com"
```

### 快捷键

Markdown-Writer提供了大量的快捷键和命令来增强md文件的编辑体验.
要启用这些快捷键, 需要执行命令Markdown Writer: Create Default Keymaps.
该命令会自动将Markdown-Writer的默认热键添加到keymap.cson中. 就像这个样子

```a
".platform-linux atom-text-editor:not([mini])":
  "shift-ctrl-K": "markdown-writer:insert-link"
  "shift-ctrl-I": "markdown-writer:insert-image"
  "ctrl-i":       "markdown-writer:toggle-italic-text"
  "ctrl-b":       "markdown-writer:toggle-bold-text"
  "ctrl-'":       "markdown-writer:toggle-code-text"
  "ctrl-h":       "markdown-writer:toggle-strikethrough-text"
  "ctrl-1":       "markdown-writer:toggle-h1"
  "ctrl-2":       "markdown-writer:toggle-h2"
  "ctrl-3":       "markdown-writer:toggle-h3"
  "ctrl-4":       "markdown-writer:toggle-h4"
  "ctrl-5":       "markdown-writer:toggle-h5"
```

可以发现这些热键包括插入链接, 图片, 切换各种字体样式.

如果你和我一样使用vim-mode插件, 还可以添加这些热键

```a
"atom-text-editor.vim-mode.normal-mode":
  "g x": "markdown-writer:open-link-in-browser"
  "g k": "markdown-writer:jump-to-reference-definition"
  "[ h": "markdown-writer:jump-to-previous-heading"
  "] h": "markdown-writer:jump-to-next-heading"
  ", o": "markdown-writer:toggle-ol"
  ", u": "markdown-writer:toggle-ul"
  ", t": "markdown-writer:toggle-task"
  ", T": "markdown-writer:toggle-taskdone"

"atom-text-editor.vim-mode.insert-mode":
  "| i": "markdown-writer:insert-table"
  "| |": "markdown-writer:jump-to-next-table-cell"

"atom-text-editor.vim-mode.visual-mode":
  "_": "markdown-writer:toggle-italic-text"
  "8": "markdown-writer:toggle-bold-text"
  "`": "markdown-writer:toggle-code-text"
```

下面列出上文还没有提到的功能列表, 请各位同学自行选择需要的功能并设为热键吧

```a
# 工作区
"markdown-writer:new-post",
"markdown-writer:new-draft",
"markdown-writer:open-cheat-sheet",
"markdown-writer:create-default-keymaps",
"markdown-writer:create-project-configs"
# 编辑区
"markdown-writer:manage-post-tags",
"markdown-writer:manage-post-categories",
"markdown-writer:insert-footnote",
"markdown-writer:toggle-codeblock-text",
"markdown-writer:toggle-keystroke-text",
"markdown-writer:toggle-blockquote",
"markdown-writer:publish-draft",
"markdown-writer:format-table",
"markdown-writer:correct-order-list-numbers",
"markdown-writer:insert-new-line",
"markdown-writer:indent-list-line"
```

这些命令的名字都很明白, 就不一一解释了.

## Markdown Preview Enhanced

该插件是Markdown Preview的增强版, 在原生插件的基础上增加了很多实用的功能

### 安装

```a
apm install markdown-preview-enhanced
```

在插件页面禁用内置的Markdown Preview插件

### 使用

该插件的功能很多, 这里只列出一些最常用的功能, 更多功能请参考中文官方文档
1. 预览md的快捷键任然为Ctrl+Shift+M
2. 编辑预览同步滚动
3. 命令Create Toc可以在当前位置生成md文件的toc
4. md文件导出为PDF, PNG, JPEG等文件
5. 命令Insert Table用于插入表格
6. 在预览窗口右键可以选择在浏览器中打开预览
7. 支持GitHub Flavored Markdown样式的TODO List

### 配置

下面是我的配置

```a
"*":
  "markdown-preview-enhanced":
    breakOnSingleNewline: true
    useGitHubStyle: false
    useGitHubSyntaxTheme: false
```

有了以上两个插件, Atom已经可以被称作最好的MD编辑器了.
