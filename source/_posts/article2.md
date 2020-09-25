---
title: 我的HexoBlog的诞生（二）
date: 2020-01-24 22:53:32
tags:
 - Hexo v4.2.1
 - NexT v7.7.0
 - Windows 10
categories: 
 - 个人静态博客搭建
---

　　本文记录和讲解一下我的HexoBlog是如何个性化设置和配置的，可供大家参考，会持续更新。关于NexT这一主题的具体使用，大家还需参考[NexT官方博客](https://theme-next.org/)、[NexT官方文档](http://theme-next.iissnan.com/getting-started.html)和搜索引擎。

　　小技巧：个性化设置和配置了一处我的HexoBlog，可以通过本地部署我的HexoBlog的方式（即在<存储HexoBlog的文件夹>下进入终端，输入`hexo s`）观察相应效果，修改一处，刷新一下，这样比较方便，等都设置和配置完毕了再部署。

<!--more-->

## Hexo的个性化设置和配置

### NexT的下载和配置

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令，等待NexT下载到当前文件夹下themes下next下。

```bash
git clone https://github.com/theme-next/hexo-theme-next themes/next
```

　　下载完成后，在<存储HexoBlog的文件夹>下找到_config.yml，此为Hexo的配置文件，打开它，找到theme，设置其值为next，如下图所示（注意在项和值之间有一个空格）。

![theme项的设置](theme项的设置.png)

### 配置站点信息

　　打开Hexo的配置文件，在上方有几项，按照下图的对照关系，个性化配置。

![个性化配置](个性化配置.png)

![个性化配置效果图](个性化配置效果图.png)

### 开启每篇文章的资源文件夹

　　打开Hexo的配置文件，关键字post_asset_folder查找，将post_asset_folder的值改为true。每次新生成layout（layout默认有 post、page 和 draft三种 ）时都会在对应生成的Markdown文件同级目录下生成一个对应的资源文件夹，将图片、音乐或视频存入该文件夹，这样，想插入图片、音乐或视频时直接填写图片、音乐或视频的完整文件名即可。

### 在文章内插入视频

　　在[存储HexoBlog的文件夹]下进入终端，输入如下命令安装 hexo-tag-dplayer。

```bash
cnpm install --save hexo-tag-dplayer
```

　　打开Hexo的配置文件，在最下面接着增加以下内容：

```
hexo-tag-dplayer:
  cdn:
    - https://cdn.jsdelivr.net/npm/dplayer/dist/DPlayer.min.js
    - https://cdn.jsdelivr.net/npm/dplayer/dist/DPlayer.min.css
  default:
    api: https://api.prprpr.me/dplayer/
    loop: yes
    screenshot: yes
```

　　使用hexo-tag-dplayer在博客文章中插入视频非常简单，先将要插入的视频文件放入每篇文章的资源文件夹中，再将以下标记插入在对应的Markdown文件合适位置即可。

```markdown
{% dplayer "url=<要插入的视频文件的完整文件名>" %}
```

### 增加本地搜索功能

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令安装hexo-generator-searchdb模块。

```bash
cnpm install --save hexo-generator-searchdb
```

　　打开Hexo的配置文件，在最下面接着增加以下内容：

```
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```

　　开启本地搜索功能：打开NexT的配置文件，关键字local_search查找，设置enable为true即可。具体操作如下视频：

{% dplayer "url=增加本地搜索功能.mp4" %}

## NexT的个性化设置与配置

### 添加菜单项并创建相应页面

　　在<存储HexoBlog的文件夹>\themes\next中也有一个_config.yml，此为NexT的配置文件，打开它，关键字menu查找，默认有home（首页）项和archives（归档）项，我的博客添加了tags（标签）和categories（分类），只需将前面的#去掉即可，如下图。

![选择菜单项](选择菜单项.png)

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令分别创建上述两菜单项页面，分别执行完毕后，会分别显示出在某一路径下生成了一个index.md，分别编辑生成的index.md，将title的值分别改为标签和分类，再在下一行分别添加type: tags和type: categories。

```bash
#创建标签页面
hexo new page tags
```

```bash
#创建分类页面
hexo new page categories
```

　　编辑<存储HexoBlog的文件夹>\scaffold下的post.md，在下一行增加tags:，再在下一行增加categories:，该文件 为模板文件，它定义了每新生成的一篇文章的Markdown文件（输入`hexo new post[自定义md文件名]`可创建一篇文章）的初始样子，我们在编辑新生成的Markdown文件时，只需自定义tags和categories的值，该文章就会在标签页面和分类页面被标记和分类起来。

### 选择主题风格

　　打开NexT的配置文件，关键字Scheme Settings查找出如下图内容，一共有四个风格供选择，可自行选择其中一个，如下图。

![SchemeSettings](SchemeSettings.png)

### 头像

　　选择一张图片，放在[存储HexoBlog的文件夹]\themes\next\source\images下，打开NexT的配置文件，关键字avatar查找，配置url为/images/[完整的图片名]，rounded和rotated设为true，如下图。

![](作者头像的配置.png)

### 回到顶部按钮设置

　　打开NexT的配置文件，关键字back2top查找，按如下图所示设置，这样回到顶部按钮显示在侧边栏且显示有百分比。

![](回到顶部按钮设置.png)

### 添加友情链接

　　打开NexT的配置文件，关键字links查找，添加友情链接。具体操作如下视频：

{% dplayer "url=添加友情链接.mp4" %}

### 下载并开启fancybox功能（查看图片功能）

　　进入<存储HexoBlog的文件夹>\themes\next\source\lib下，右键，选择Git Bash Here进入终端，输入如下命令下载fancybox，再打开NexT的配置文件，关键字fancybox查找，开启fancybox功能。具体操作如下视频：

```
git clone https://github.com/theme-next/theme-next-fancybox3 fancybox
```

{% dplayer "url=开启fancybox功能.mp4" %}

### 添加联系方式

　　打开NexT的配置文件，关键字social查找，添加自己的qq邮箱，如下图。

![](添加联系方式.png)

### 添加 Valine 评论系统

　　Valine是基于LeanCloud的，首先需要[注册LeanCloud账号](https://leancloud.cn/dashboard/login.html)，注意需要验证邮箱，注册成功后进入控制台，需要先实名认证，认证成功后，点击创建应用，新应用名称就填Valine，选择开发版，点击创建，点击存储图标，点击创建Class，Class名称填Comment，添加，再点击创建Class，Class名称填Counter，添加，创建Class成功后如下图。

![](创建Class.png)

　　点击左边的设置，点击安全中心，服务开关里仅打开数据存储服务，Web安全域名中填写自己的博客地址，保存，点击左侧应用keys，获取到App ID和App key。

　　打开NexT的配置文件，关键字valine查找，设置comments下的active为valine，再点击查找下一个，设置valine下的enable为true，配置valine下的appid和appkey为获取到的App ID和App key，设置valine下的language为zh-cn，再点击一次查找下一个，配置valine为以下地址，如下图。

```
https://cdn.jsdelivr.net/npm/valine@1.3.10/dist/Valine.min.js
```

![](valine.png)

### 加入豆瓣页面

　　在<存储HexoBlog的文件夹>下进入终端，输入如下命令安装hexo-douban模块。

```bash
cnpm install --save hexo-douban
```

　　打开Hexo的配置文件，在最下面接着增加以下内容：

```
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
```

　　可以测试一下，`hexo s`，地址栏输入 http://localhost:4000/books ，确认是否访问正常。

　　添加图书、电影和游戏的菜单项，打开NexT的配置文件，关键字menu查找，添加books项、movies项和games项，如下。

```diff
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

![添加豆瓣页面菜单项](添加豆瓣页面菜单项.png)

　　在<存储HexoBlog的文件夹>\themes\next\languages下找到zh-CN.yml，menu处，添加books项、movies项和games项对应的翻译，如下图。

![添加豆瓣页面菜单项简体中文翻译](添加豆瓣页面菜单项简体中文翻译.png)

