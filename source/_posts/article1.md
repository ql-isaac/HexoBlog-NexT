---
title: 我的HexoBlog的诞生（一）
date: 2020-01-24 22:53:24
tags:
 - Hexo v4.2.1
 - Git v2.25.0.windows.1
 - GitHub
 - Node.js v12.14.0
 - Windows 10
categories: 
 - 我的HexoBlog的诞生
---

　　本文记录和讲解一下我的HexoBlog是如何一步一步被部署至Github Pages上的，可供大家参考。部署完成后可参考我的下一篇文章《我的HexoBlog的诞生（二）》对自己的HexoBlog进行个性化设置和配置，不过在此之前，需阅读[Hexo官方文档](https://hexo.io/zh-cn/docs/)，对Hexo有基本的完整的认识。

<!--more-->

### 注册我的Github账户，建立Github Pages

1. 进入[Github首页](http://github.com/)，点击Sign up注册，填写Username等，验证邮箱，注册成功；
2. 点击右上角的加号，点击New repository，填写Repository name，这里的仓库名必须要按照”<我的Github用户名>.github.io“的格式来填，填写Description，点击Creat repository，创建Github Pages成功。

### 安装Node.js，安装Git和Git的配置

3. 进入[Node.js官方网站](https://nodejs.org/)，点击下载LTX（Long Term Support）版，我下载的是v12.14.0版本的，安装步骤非常简单，一直next；

4. 进入[Git官方网站下载页面](https://git-scm.com/downloads)，选择64位Windows版本的Git下载，安装步骤也是一直next，安装好后需要进行全局用户信息的配置，在桌面右键，选择Git Bash Here进入终端，配置命令如下，分别执行即可，执行后没任何提示就说明执行成功；

   ```bash
   git config --global user.name "<我的Github用户名>"
   ```

   ```bash
   git config --global user.email "<我的Github邮箱>"
   ```

5. 接着在终端输入`ssh-keygen -t rsa`，按3个回车，此时打开[.ssh 文件夹](C:\\Users\\<我的Windows用户名>\\.ssh)，用文本编辑器打开id_rsa.pub，Ctrl+A复制里面全部的内容；

6. 进入浏览器，进入Github，点击右上角的头像，点击Setting，点击左侧的SSH and GPG keys，点击右侧的New SSH key，填写Tile，也可以不填，填写Key，右键粘贴，粘贴刚复制的内容，最后点击Add SSH key。

7. 测试本地和Github的SSH配置是否正确，打开终端输入`ssh -T git@github.com`回车，输入yes，回车，看到一句提示信息：Hi <我的Github用户名>! You've successfully authenticated, but GitHub does not provide shell access，配置成功。

### 安装Hexo

8. 在合适的路径下新建一个文件夹，文件夹名自定义，例如HexoBlog，作为<存储HexoBlog的文件夹>；

9. 打开<存储HexoBlog的文件夹>，在空白处点鼠标的右键，选择Git Bash Here进入终端；

10. 安装cnpm提高下载速度，以后下载插件都可用cnpm（即将下载某一个插件的命令中的npm改为cnpm）。在终端输入如下命令，回车，等待cnpm下载完成；

   ```bash
   npm install -g cnpm --registry=http://registry.npm.taobao.org
   ```

11. 在终端输入如下命令，回车，等待hexo-cli下载完成，可输入`hexo -v`查看相关信息；

   ```bash
   cnpm install -g hexo-cli
   ```

12. 在终端输入`hexo init`，等待，可在<存储HexoBlog的文件夹>中看到生成了如下图所示的文件。

    ![初始文件](https://image.ql-isaac.cn/初始文件.png)

### 本地部署我的HexoBlog

13. 在终端输入`hexo s`，打开浏览器，输入localhost:4000，可看到本地部署的我的HexoBlog，如下图所示，Ctrl+C停止运行；

    ![本地部署的我的HexoBlog](https://image.ql-isaac.cn/本地部署的我的HexoBlog.png)

### 部署至Github Pages

14. 安装Hexo的Git插件。终端输入如下命令，回车，等待下载完成。

   ```bash
   cnpm install --save hexo-deployer-git
   ```

15. 进入<存储HexoBlog的文件夹>，用文本编辑器打开_config.yml，在最下面找到“deploy:"，补充成如下内容，保存关闭：

   ```
   deploy:  
     type: git  
     repo: git@github.com:<我的Github用户名>/<我的Github用户名>.github.io.git         
     branch: master
   ```

16. 在终端输入`hexo g -d`，回车，进行博客的最终操作——生成静态文件后立即部署到Github Pages上（建议每次想把本地博客上传到Gihub Pages时，都使用该命令）。

17. [大功告成](https://ql-isaac.github.io)（将ql-isaac替换成自己的Github用户名）。


### 参考资料

https://blog.csdn.net/huangqqdy/article/details/83032408
https://caiyantao.gitee.io/2019/04/13/Hexo-%E4%B8%80
https://caiyantao.gitee.io/2019/04/13/Hexo-一/
https://caiyantao.gitee.io/2019/04/13/Hexo%EF%BC%88%E4%BA%8C%EF%BC%89/#more
https://caiyantao.gitee.io/2019/04/13/Hexo（二）/#more
https://www.bilibili.com/video/av44544186?from=search&seid=9508828059673681599
