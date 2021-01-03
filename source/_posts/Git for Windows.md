---
title: Git for Windows
date: 2021-01-03 15:27:43

tags:
 - Windows 10 企业版 LTSC
categories: 
 - Git和GitHub从入门到实践
---

来记录一下Git for Windows的使用。

<!--more-->

{% note success %}2020-1-3{% endnote %}

　　每次打开VS Code时右下角总提示这个，还是更新一下吧，直接点击更新GIT。

![image-20210103170629005](https://image.ql-isaac.cn/Git-for-Windows/image-20210103170629005.png)

　　原来是跳转到Git的官方网站。

![image-20210103171041063](https://image.ql-isaac.cn/Git-for-Windows/image-20210103171041063.png)

{% note warning %}这里会跳转到IE浏览器，呵呵，赶紧在所有设置-应用-默认应用中把Web浏览器设置成Microsoft Edge再打开Git官网。{% endnote %}

![image-20210103171326828](https://image.ql-isaac.cn/Git-for-Windows/image-20210103171326828.png)

　　常规操作：下载，双击安装。

![image-20210103171653864](https://image.ql-isaac.cn/Git-for-Windows/image-20210103171653864.png)

　　Only show new option，嗯，很人性化！好评！

![image-20210103172647714](https://image.ql-isaac.cn/Git-for-Windows/image-20210103172647714.png)

　　勾选第二个，以后用`git init`初始化的默认分支名就为main了。

{% note info %}由于某些原因，2020年10月1日，GitHub将启用main作为默认分支名，master将成为历史！{% endnote %}

![image-20210103173648360](https://image.ql-isaac.cn/Git-for-Windows/image-20210103173648360.png)

　　这个，直接Next，默认即可。

![image-20210103174355777](https://image.ql-isaac.cn/Git-for-Windows/image-20210103174355777.png)

　　credential helper，凭据帮助器？这是个什么玩意儿？start一下这个[cross-platform version of the Git Credential Manager](https://github.com/microsoft/Git-Credential-Manager-Core)先，有时间看看（虽然看不懂）。

![image-20210103175247449](https://image.ql-isaac.cn/Git-for-Windows/image-20210103175247449.png)

　　安装中。

![image-20210103175314904](https://image.ql-isaac.cn/Git-for-Windows/image-20210103175314904.png)

　　完成。

![image-20210103175423993](https://image.ql-isaac.cn/Git-for-Windows/image-20210103175423993.png)

　　Release Notes:

![image-20210103175546812](https://image.ql-isaac.cn/Git-for-Windows/image-20210103175546812.png)