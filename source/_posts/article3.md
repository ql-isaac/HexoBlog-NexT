---
title: 我的HexoBlog的诞生（三）
date: 2020-01-24 22:53:39
tags:
 - Hexo v4.2.1
 - Markdown
 - Windows 10
categories: 我的HexoBlog的诞生
---

　　本文记录和讲解我的HexoBlog的使用，会持续更新。

<!--more-->

## 使用Typora编辑Markdown文件，书写博客文章

　　通过执行`hexo new post <自定义md文件名>`，相应生成的[自定义md文件名].md这一Markdown文件将在_posts下生成，那么该如何编辑这种Markdown文件，书写自己的博客文章呢？

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
{% dplayer "url=标题.mp4" %}

### 列表

　　经常用的是有序列表和无序列表。使用`<序号>.`+空格可表示有序列表，回车自动生成下一项，如下图。

![有序列表](有序列表.gif)

　　使用`-`+空格可表示无序列表，回车自动生成下一项，如下图。

![无序列表](无序列表.gif)

　　还有一个任务列表，使用`- [ ]`+空格可表示任务列表，回车自动生成下一项，如下图。

![任务列表](任务列表.gif)                s                         

## 部署在Github Pages上太慢了！



