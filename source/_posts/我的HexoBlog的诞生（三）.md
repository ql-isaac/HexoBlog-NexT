---
title: 我的HexoBlog的诞生（三）
date: 2020-01-24 22:53:39
cover: https://image.ql-isaac.cn/Blogging-bro.png
tags:
 - Windows 10 企业版 LTSC
 - Hexo v4.2.1
 - Markdown
 - Typora
categories:
 - 我的HexoBlog的诞生
---

　　本文记录和讲解我的HexoBlog的使用，会持续更新。

<!-- more -->

## 使用Typora编辑Markdown文件，书写博客文章

　　通过执行`hexo new post <自定义md文件名>`，相应Markdown文件将在_posts下生成，那么该如何编辑这种Markdown文件，书写自己的博客文章呢？

### Markdown

　　Markdown是一种轻量级的标记语言，类似于HTML，但Markdown的语法十分简单，常用的标记符号也不超过十个。

### Typora

　　Typora是一个Markdown文件阅读器与编辑器，支持MacOS、Windows、Linux平台，可到[Typora 官网](https://typora.io/)下载。

### 标题

　　使用`#`可表示1-6级标题。一级标题对应一个#，二级标题对应两个# ，以此类推，如下视频（注意#后面有一个空格）。

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
```

{% dplayer "url=https://image.ql-isaac.cn/%E6%A0%87%E9%A2%98.mp4" %}

### 列表

　　经常用的是有序列表和无序列表。使用`<序号>. `（`.`后面有一个空格）可表示有序列表，回车自动生成下一项，如下图。

![有序列表](https://image.ql-isaac.cn/有序列表.gif)

　　使用`- `（`-`后面有空格）可表示无序列表，回车自动生成下一项，如下图。

![无序列表](https://image.ql-isaac.cn/无序列表.gif)

　　还有一个任务列表，使用`- [ ] `（`[ ]`后面有空格）可表示任务列表，回车自动生成下一项，如下图。

![任务列表](https://image.ql-isaac.cn/任务列表.gif)

## 如何在文章中插入图片、视频和音乐？

### 开启每篇文章的资源文件夹

　　打开Hexo的配置文件，关键字post_asset_folder查找，将post_asset_folder的值改为true。每次新生成layout（layout默认有 post、page 和 draft三种 ）时都会在对应生成的Markdown文件同级目录下生成一个对应的资源文件夹，可将图片、音乐或视频存入该文件夹，这样，想插入图片、音乐或视频时直接填写图片、音乐或视频的完整文件名即可。

### 在文章内插入视频

　　在[存储HexoBlog的文件夹]下进入终端，输入如下命令安装 hexo-tag-dplayer。

```bash
cnpm install --save hexo-tag-dplayer
```

　　编辑Hexo的配置文件，如下：

```diff
# 本行为<存储HexoBlog的文件夹>\_config.yml的第99行
deploy:  
  type: git  
  repo: git@github.com:<我的Github用户名>/<我的Github用户名>.github.io.git         
  branch: master

search:
  path: search.xml
  field: post
  format: html
  limit: 10000

douban:
  user: <豆瓣ID>
  builtin: true
  book:
    title: <书籍页面的标题>
    quote: <开头的引言>
  movie:
    title: <电影页面的标题>
    quote: <开头的引言>
  game:
    title: <游戏页面的标题>
    quote: <开头的引言>
  timeout: 10000

+hexo-tag-dplayer:
+  cdn:
+    - https://cdn.jsdelivr.net/npm/dplayer/dist/DPlayer.min.js
+    - https://cdn.jsdelivr.net/npm/dplayer/dist/DPlayer.min.css
+  default:
+    api: https://api.prprpr.me/dplayer/
+    loop: yes
+    screenshot: yes
```

　　使用hexo-tag-dplayer在博客文章中插入视频非常简单，先将要插入的视频文件放入每篇文章的资源文件夹中，再将以下标记插入在对应的Markdown文件合适位置即可。

```markdown
{% dplayer "url=<要插入的视频文件的完整文件名>" %}
```

## 部署在Github Pages上太慢了！



