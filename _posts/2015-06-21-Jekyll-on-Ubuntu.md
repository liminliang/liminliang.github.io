---
layout: post
title: "Ubuntu下搭建Jekyll运行平台"
category: Web技术
tags: [web, Ubuntu, Jekyll]
---
![](/assets/img/github.png)

&emsp;&emsp;本文假设你已经具备Ubuntu（或Linux，在写本篇博客时，我用的是Ubuntu 15.04的版本）的基本操作，同时已经在GitHub上拥有个人账号（**并且已经建立了一个名为：username.github.io的repository**），并且已经能够通过个人电脑进行远程SSH登录。

##### (1) 安装Ruby
    $ sudo apt-get install ruby
    $ sudo apt-get install ruby-dev
\n\n\n

##### (2) 设置国内Ruby源
&emsp;&emsp;由于国内使用ruby官方源会出现无法连接的问题，因此需要将其源设置为淘宝服务器的源。

    $ gem sources -r https://rubygems.org/
    $ gem sources -a http://ruby.taobao.org/
    $ gem sources -u

&emsp;&emsp;上述代码的最后一行经过更新源的缓存以后，即完成了Ruby的gem源的更改。

##### (3) 安装nodejs
    $ sudo apt-get install nodejs

##### (4) 安装Jekyll
&emsp;&emsp;如果在安装过程中系统提示没有安装`rdoc`，`rdiscount`，`kramdown`等，可以执行下面步骤安装

    $ sudo gem install jekyll
    $ sudo gem install kramdown
    $ sudo gem install rdoc
    $ sudo gem install rdiscount

##### (5)运行Jekyll server
&emsp;&emsp;安装完成以后，本地jekyll环境就搭建完成了，进入个人博客的根目录，运行下面的命令即可启动jekyll服务器。

    $ jekyll server

在浏览器中输入：http://localhost:4000即可显示

##### (6) Git的安装与使用
&emsp;&emsp;在本地环境编写和调试后的网页代码和文件，需要通过Git跟GitHub链接传送。首先，需要在Ubuntu上安装Git：

    $ sudo apt-get install git

上传博客到GitHub，在blog所在文件夹内

    $ git init
    $ git add .
    $ git commit -m “initialization”
    $ git remote add origin https://github.com/USERNAME/USERNAME.github.io.git
    $ git push -u origin master

上传成功后，利用*USERNAME.github.io*的域名就可以看到网页。

##### (7) 参考内容
> [[1] http://coolshell.info/blog/2015/03/github-pages-blog.html](http://coolshell.info/blog/2015/03/github-pages-blog.html)

> [[2] http://havee.me/](http://havee.me/)

> [[3] http://wowubuntu.com/markdown/](http://wowubuntu.com/markdown/)

> [[4] http://www.jianshu.com/p/q81RER](http://www.jianshu.com/p/q81RER)

