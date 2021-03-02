---
layout: mypost
title: 部署kodexplorer私有云盘
categories: [收藏夹]
---
# Ubuntu服务器上部署kodexplorer私有云盘

------

> * 文章主要内容：kodexplorer私有云盘部署在Ubuntu 教程

## 一、准备

注意：云服务器部署和普通的Ubuntu上部署有一些区别，因为云服务器上只能使用命令行，没有界面。

首先，你得在阿里云上有一台云服务器，并且确定所安装的系统是什么，可通过 getconf LONG_BIT命令确定Ubuntu系统版本。整个过程在终端通过命令完成。

## 二、下载安装xampp
1.什么是xampp？
XAMPP（Apache+MySQL+PHP+PERL）是一个功能强大的建站集成软件包。这个软件包原来的名字是 LAMPP，但是为了避免误解，最新的几个版本就改名为 XAMPP 了。它可以在Windows、Linux、Solaris、Mac OS X 等多种操作系统下安装使用，支持多语言：英文、简体中文、繁体中文、韩文、俄文、日文等。

2.下载与操作系统版本对应的xampp

找到想下载的版本，鼠标右键复制下载链接。在云服务器终端输出命令：wget -c 下载链接。这里我下载最新版本，命令为：

```Python
wget -c https://www.apachefriends.org/xampp-files/5.6.35/xampp-linux-x64-5.6.35-0-installer.run
```

下载完成后，在当前目录可以看到一个.run可执行文件，先给文件添加相应的权限，命令为：

chmod +x xampp-linux-x64-5.6.35-0-installer.run
3.安装xampp
命令为：

sudo ./xampp-linux-x64-5.6.35-0-installer.run
按照要求输入Y或者按回车键就可以安装成功，它的默认安装位置为：/opt/lampp。

4.启动与停止xampp
（1）启动xampp，命令为：

sudo /opt/lampp/xampp start
在启动之后，可以在自己的电脑或手机浏览器上输入你的云服务器IP地址，就可以看到xampp的默认页面，代表你的xampp正常使用，默认端口为80。运行出现错误，可能是端口冲突，通过查看80端口和443端口（命令为netstat -ap | grep 80）使用情况，可以修改默认的80和443端口。

（2）停止xampp，命令为：sudo /opt/lampp/xampp stop。

## 三、下载安装可道云kodexplorer
1.下载最新版可道云，其中有Linux获取最新版可道云的相关命令。

下载命令：

wget http://static.kodcloud.com/update/download/kodexplorer4.37.zip
创建目录：

sudo mkdir kodexplorer
解压命令：

unzip kodexplorer4.25.zip -d ./kodexplorer
进入对应文件夹，并设置权限：

cd ./kodexplorer，chmod -Rf 777 ./*
2.拷贝至相应的目录
命令：

sudo cp -r kodexplorer/ /opt/lampp/htdocs/。
进入对应文件夹，设置权限：

cd /opt/lampp/htdocs
chmod 777 kodexplorer
chmod -R 777 kodexplorer/data/
3.测试是否成功
重新启动xampp服务，浏览器打开“IP地址/kodexplorer/index.php”，设置管理员密码，开始使用。

![此处输入图片的描述][1]


  [1]: http://static.zuidaima.com/images/317632/201901/20190104152310242.gif