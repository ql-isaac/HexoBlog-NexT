---
title: 我的HexoBlog的诞生（二）
date: 2020-01-24 22:53:32
tags:
 - Windows 10 企业版 LTSC
 - Hexo v4.2.1
 - NexT v7.7.0
categories: 
 - 我的HexoBlog的诞生
---

　　本文记录和讲解一下我的HexoBlog是如何个性化设置和配置的，可供大家参考，会持续更新。关于NexT这一主题的具体使用，大家还需参考[NexT官方博客](https://theme-next.org/)、[NexT官方文档](http://theme-next.iissnan.com/getting-started.html)和搜索引擎。

　　小技巧：个性化设置和配置了一处我的HexoBlog，可以通过本地部署我的HexoBlog的方式（即在<存储HexoBlog的文件夹>下进入终端，输入`hexo s`）观察相应效果，甚至可以修改一处，刷新一下查看效果，等都设置和配置完毕了再部署。

<!--more-->

## Hexo的个性化设置和配置

### NexT的下载和设置

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令，等待NexT下载到当前文件夹下themes下next下。

```bash
git clone https://github.com/theme-next/hexo-theme-next themes/next
```

　　下载完成后，在<存储HexoBlog的文件夹>下找到_config.yml，此为Hexo的配置文件，打开它，找到theme，设置其值为next，如下图所示（注意在项和值之间有一个空格）。

![theme项的设置](https://image.ql-isaac.cn/theme项的设置.png)

### 配置站点信息

　　打开Hexo的配置文件，在上方有几项，按照下图的对照关系，个性化配置。

![个性化配置](https://image.ql-isaac.cn/个性化配置.png)

![个性化配置效果图](https://image.ql-isaac.cn/个性化配置效果图.png)

## NexT的个性化设置与配置

### 增加本地搜索功能

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令安装hexo-generator-searchdb模块。

```bash
cnpm install --save hexo-generator-searchdb
```

　　编辑Hexo的配置文件，如下：

```diff
# 本行为<存储HexoBlog的文件夹>\_config.yml的第99行
deploy:  
  type: git  
  repo: git@github.com:<我的Github用户名>/<我的Github用户名>.github.io.git         
  branch: master
+
+search:
+  path: search.xml
+  field: post
+  format: html
+  limit: 10000
```

　　开启本地搜索功能：打开NexT的配置文件，关键字local_search查找，设置enable为true即可。具体操作如下视频：

{% dplayer "url=https://image.ql-isaac.cn/%E5%A2%9E%E5%8A%A0%E6%9C%AC%E5%9C%B0%E6%90%9C%E7%B4%A2%E5%8A%9F%E8%83%BD.mp4" %}

### 添加菜单项并创建相应页面

　　在<存储HexoBlog的文件夹>下themes下next中也有一个_config.yml，此为NexT的配置文件，打开它，关键字menu查找，默认有home（首页）项和archives（归档）项，要想添加tags（标签）项和categories（分类）项，只需将前面的#去掉即可，如下图。

![选择菜单项](https://image.ql-isaac.cn/选择菜单项.png)

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令分别创建上述两菜单项的页面，分别执行完毕后，会分别显示出在哪一路径下生成了一个index.md，分别编辑生成的index.md，将title的值分别改为标签和分类，再在下一行分别添加type: tags和type: categories。

```bash
hexo new page tags #创建标签页面
```

```bash
hexo new page categories #创建分类页面
```

　　编辑<存储HexoBlog的文件夹>下scaffold下的post.md，在下一行增加tags:，再在下一行增加categories:，该文件为模板文件，它定义了每新生成的一篇文章（输入`hexo new post <自定义md文件名>`可创建一篇文章）的初始样子，我们在编辑新文章的Markdown文件时，只需自定义tags和categories的值，该文章就会在标签页面和分类页面被标记和分类起来。

### 选择主题风格

　　打开NexT的配置文件，关键字Scheme Settings查找出如下图内容，一共有四个风格供选择，可自行选择其中一个，如下图。

![SchemeSettings](https://image.ql-isaac.cn/SchemeSettings.png)

### 头像

　　选择一张图片，放在<存储HexoBlog的文件夹>下themes下next下source下images下，打开NexT的配置文件，关键字avatar查找，按下图配置，效果图如下。



![avatar](https://image.ql-isaac.cn/avatar.png)

![作者头像](https://image.ql-isaac.cn/作者头像.png)

### 回到顶部按钮设置

　　打开NexT的配置文件，关键字back2top查找，按如下图所示设置，这样回到顶部按钮显示在侧边栏且显示有百分比。

![回到顶部按钮设置](https://image.ql-isaac.cn/回到顶部按钮设置.png)

### 添加友情链接

　　打开NexT的配置文件，关键字links查找，添加友情链接。具体操作如下视频：

{% dplayer "url=https://image.ql-isaac.cn/%E6%B7%BB%E5%8A%A0%E5%8F%8B%E6%83%85%E9%93%BE%E6%8E%A5.mp4" %}

### 下载并开启fancybox功能（查看图片功能）

　　进入<存储HexoBlog的文件夹>下themes下next下source下lib下，右键，选择Git Bash Here进入终端，输入如下命令下载fancybox，再打开NexT的配置文件，关键字fancybox查找，开启fancybox功能。具体操作如下视频：

```
git clone https://github.com/theme-next/theme-next-fancybox3 fancybox
```

{% dplayer "url=https://image.ql-isaac.cn/%E5%BC%80%E5%90%AFfancybox%E5%8A%9F%E8%83%BD.mp4" %}

### 添加联系方式

　　打开NexT的配置文件，关键字social查找，添加自己的qq邮箱，如下图。

![](https://image.ql-isaac.cn/添加联系方式.png)

### 添加 Valine 评论系统

　　Valine是基于LeanCloud的，首先需要[注册LeanCloud账号](https://leancloud.cn/dashboard/login.html)，注意需要验证邮箱，注册成功后进入控制台，需要先实名认证，认证成功后，点击创建应用，新应用名称就填Valine，选择开发版，点击创建，点击存储图标，点击创建Class，Class名称填Comment，添加，再点击创建Class，Class名称填Counter，添加，创建Class成功后如下图。

![](https://image.ql-isaac.cn/创建Class.png)

　　点击左边的设置，点击安全中心，服务开关里仅打开数据存储服务，Web安全域名中填写自己的博客地址，保存，点击左侧应用keys，获取到App ID和App key。

　　打开NexT的配置文件，关键字valine查找，设置comments下的active为valine，再点击查找下一个，设置valine下的enable为true，配置valine下的appid和appkey为获取到的App ID和App key，设置valine下的language为zh-cn，再点击一次查找下一个，配置valine为以下地址，如下图。

```
https://cdn.jsdelivr.net/npm/valine@1.3.10/dist/Valine.min.js
```

![](https://image.ql-isaac.cn/valine.png)

### 加入豆瓣页面

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令安装hexo-douban模块。

```bash
cnpm install --save hexo-douban
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

+douban:
+  user: <豆瓣ID>
+  builtin: true
+  book:
+    title: <书籍页面的标题>
+    quote: <开头的引言>
+  movie:
+    title: <电影页面的标题>
+    quote: <开头的引言>
+  game:
+    title: <游戏页面的标题>
+    quote: <开头的引言>
+  timeout: 10000
```

　　添加图书、电影和游戏的菜单项。打开NexT的配置文件，关键字menu查找，添加books项、movies项和games项，如下。

```diff
# 本行为<存储HexoBlog的文件夹>\themes\next\_config.yml的121行
 menu:
   home: / || home
   #about: /about/ || user
   tags: /tags/ || tags
   categories: /categories/ || th
   archives: /archives/ || archive
   #schedule: /schedule/ || calendar
   #sitemap: /sitemap.xml || sitemap
   #commonweal: /404/ || heartbeat
+  books: /books || <Font Awesome图标>
+  movies: /movies || <Font Awesome图标>
+  games: /games || <Font Awesome图标>
```

![添加豆瓣页面菜单项](https://image.ql-isaac.cn/添加豆瓣页面菜单项.png)

　　在<存储HexoBlog的文件夹>下themes下next下languages下找到zh-CN.yml，menu处，添加books项、movies项和games项对应的翻译，如下图。

![添加豆瓣页面菜单项简体中文翻译](https://image.ql-isaac.cn/添加豆瓣页面菜单项简体中文翻译.png)