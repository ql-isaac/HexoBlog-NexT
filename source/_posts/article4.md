---
title: Git
date: 2020-01-24 22:53:47
tags:
 - Git v2.25.0.windows.1
 - Git v2.17.1
 - Windows 10
 - Ubuntu 18.04 LTS
categories: Git和GitHub从入门到实践
---

　　[林纳斯·托瓦兹](https://www.baidu.com/s?wd=林纳斯·托瓦兹&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)在1991年10月5日发布了开源的Linux，从此，Linux操作系统不断发展壮大，其实Linux的壮大离不开全世界热心的志愿者，他们在世界各地为Linux编写代码，那么，Linux的代码是如何管理的呢？

<!--more-->

## Git的诞生

　　在2002年以前，世界各地的志愿者还是以一种传统的方式将源代码文件发给[林纳斯·托瓦兹](https://www.baidu.com/s?wd=林纳斯·托瓦兹&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)，然后由他本人通过手工方式合并代码。当时虽然有CSV、SVN这些免费的版本控制系统，但是速度慢、需要联网，也有一些商用的版本控制系统，虽然比CSV、SVN好用，但是不开源，和Linux的开源精神不符。2002年，Linux系统已经发展了十年，代码库之大让[林纳斯·托瓦兹](https://www.baidu.com/s?wd=林纳斯·托瓦兹&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)很难继续通过手工方式管理，最终[林纳斯·托瓦兹](https://www.baidu.com/s?wd=林纳斯·托瓦兹&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)选择了一个商业的版本控制系统BitKeeper，BitKeeper的东家BitMover公司出于人道主义精神，授权Linux社区免费使用这个版本控制系统，这看起来是一个很好的局面。Linux社区牛人聚集，2005年，开发Samba的Andrew试图破解BitKeeper的协议的行为被BitMover公司发现，Linux社区的BitKeeper免费使用权被收回，于是，[林纳斯·托瓦兹](https://www.baidu.com/s?wd=林纳斯·托瓦兹&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)花了两周时间自己用C写了一个分布式版本控制系统，Git诞生！之后，Git迅速成为最流行的分布式版本控制系统，随即，2008年，GitHub网站上线，它为开源项目免费提供Git存储，无数开源项目开始迁移至GitHub，包括jQuery，PHP，Ruby等等。

## Git真的很重要



## 安装和配置Git

　　我在《我的HexoBlog的诞生（一）》中已经完成了Git的安装和配置，不过那是在Windows上，而且也没详细讲，这里就详细讲解一下如何在Windows和Linux上安装和配置Git吧。

### Windows 10上安装和配置Git

1. 以v2.25.0版Git为例，点击安装程序；

![安装程序](安装程序.png)

2. GNU许可证：不看，Next；

![许可协议](许可协议.png)

3. 设置安装路径：建议将C改为D，安装在D盘，这里就不改了，Next；

![设置安装路径](设置安装路径.png)

4. 安装组件：第一个选项是说是否创建桌面快捷方式，可以不勾选，下面六个都勾选了，为默认，不更改，倒数第一个是说是否检查更新，可以不勾选，倒数第二个是说是否在所有控制台窗口中使用TrueType字体，勾选，Next；

![安装组件](安装组件.png)

5. 开始菜单设置：直接Next；

![开始菜单设置](开始菜单设置.png)

6. 设置Git的默认文本编辑器：就选择Vim，Next；

![设置Git的默认文本编辑器](设置Git的默认文本编辑器.png)

7. 调整PATH环境：就选择默认推荐的，Next。该推荐项是说仅向PATH添加一些最小的Git包装器，以避免使用可选的Unix工具造成环境混乱，能够通过Git Bash、命令提示符、Windows PowerShell以及在PATH中寻找Git的任何第三方软件使用Git。

![调整Path环境](调整Path环境.png)

8. 选择HTTPS后端传输：第一个选项是说使用OpenSSL库，服务器证书将使用ca-bundle.crt文件进行验证，这是我们常用的选项。第二个选项是说使用本地Windows 安全通道库，服务器证书将使用Windows证书存储验证，此选项还允许使用公司的内部根CA证书，例如通过Active Directory Domain Services。这里，就默认第一个选项，Next；

![选择HTTPS后端传输](选择HTTPS后端传输.png)

9. 配置行尾符号转换：第一个选项是说签出Windows风格，提交Unix风格的行尾，签出文本文件时，Git会将LF转换为CRLF，提交文本文件时，CRLF将转换为LF，对于跨平台项目，这是Windows上的推荐设置（“ core.autocrlf”设置为“ true”）。第二个选项是说按原样签出，提交Unix样式的行尾，签出文本文件时，Git不会执行任何转换，提交文本文件时，CRLF将转换为LF，对于跨平台项目，这是Unix上的建议设置（“ core.autocrlf”设置为“ input”）。第三个选项是说按原样签出，按原样提交，当签出或提交文本文件时，Git不会执行任何转换，不建议跨平台项目选择此选项（“ core.autocrlf”设置为“ false”）。这里，就默认第一个选项，Next；

![配置行尾符号转换](配置行尾符号转换.png)

10. 配置终端模拟器以与Git Bash一起使用：第一个选项是说使用MinTTY（MSYS2的默认终端），Git Bash将使用MinTTY作为终端模拟器，该模拟器具有可调整大小的窗口，非矩形选择和Unicode字体，Windows控制台程序（例如交互式Python）必须通过“ winpty”启动才能在MinTTY中运行。第二个选项是说使用Windows的默认控制台窗口，Git将使用Windows的默认控制台窗口（“cmd.exe”），该窗口可以与Win32控制台程序（如交互式Python或node.js）一起使用，但默认的回滚非常有限，需要配置为使用unicode 字体以正确显示非ASCII字符，并且在Windows 10之前，其窗口不能自由调整大小，并且只允许矩形文本选择。这里，就默认第一个选项，Next；

![配置终端模拟器以与Git_Bash一起使用](配置终端模拟器以与Git_Bash一起使用.png)

11. 配置额外的选项：第一个选项是说启用文件系统缓存，文件系统数据将被批量读取并缓存在内存中用于某些操作（“core.fscache”设置为“true”）， 这可以显着地提升性能。第二个选项是说启用Git凭证管理器，Windows的Git凭证管理器为Windows提供安全的Git凭证存储，最显着的是对Visual Studio Team Services和GitHub的多因素身份验证支持（需要.NET Framework v4.5.1或更高版本）。第三个选项是说启用符号链接，启用符号链接需要SeCreateSymbolicLink权限，现有存储库不受此设置的影响。这里，就默认第一个和第二个选项，Install；

![配置额外的选项](配置额外的选项.png)

12. 安装完成：Next；

![安装完成](安装完成.png)

13. Release Notes：看得懂就看看吧，看不懂就关闭；

![ReleaseNotes](ReleaseNotes.png)

14. 至此Git就算安装完毕了，之后需要去[Github](https://github.com/)注册一个自己的账号，注意需要绑定自己的邮箱；

![注册](注册.png)

15. 在桌面右键，点击Git Bash Here；

![桌面右键](桌面右键.png)

16. 全局用户信息配置：分别输入以下两个命令回车执行，无提示表示命令执行成功，可以用`git config --list`来查看配置好的信息；

```bash
git config --global user.name "<自己的Github用户名>"
```

```bash
git config --global user.email "<自己的Github邮箱>"
```

17. 生成SSH秘钥：输入以下命令回车执行，然后连敲三次回车键，在C:\Users\\[你的用户名]\\.ssh下会生成以下两个文件，用文本编辑器打开id_rsa.pub，Ctrl+A复制里面全部的内容；

```bash
ssh-keygen -t rsa
```

![SSH](SSH.png)

18. Github的SSH公钥配置：登录自己的Github账号，点击右上角的头像，点击Setting，点击左侧的SSH and GPG keys，点击右侧的New SSH key，填写Tile，也可以不填，填写Key，右键粘贴，粘贴刚复制的内容，最后点击Add SSH key；

19. 测试一下，输入以下命令回车执行，输入yes，再回车，有如下提示，至此，Windows上安装和配置Git完成。

```bash
ssh -T git@github.com
```

```
Hi <自己的Github用户名>! You've successfully authenticated, but GitHub does not provide shell access.
```

### Ubuntu 18.04 LTS上安装和配置Git

1. 相比在Windows上，在Linux上安装和配置Git的步骤就比较少了。在终端输入以下命令回车执行，确保您的系统和apt包列表完全更新；

```bash
sudo apt-get update -y
```

![SSH](更新.png)

2. 在终端输入以下命令回车执行，安装Git，可输入以下命令查看Git版本；

```bash
sudo apt install git
```

```bash
git --version
```

![安装Git](安装Git.gif)

3. 全局用户信息配置：分别输入以下两个命令回车执行，无提示表示命令执行成功，可以用`git config --list`来查看配置好的信息；

```bash
git config --global user.name "<自己的Github用户名>"
```

```bash
git config --global user.email "<自己的Github邮箱>"
```

