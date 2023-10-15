---
layout: mypost
title: Debian 安装 MySQL 8.0
categories: [WEB]
---


1、更新 APT 软件源 （[MySQL REPO SITE](http://repo.mysql.com/)）


```
# 下载 APT 资源包
wget https://repo.mysql.com/mysql-apt-config_0.8.24-1_all.deb.md5
# 安装 APT 包
sudo apt-get install ./mysql-apt-config_0.8.19-1_all.deb
```

2、安装 MySQL


```
sudo apt-get update
Hit:1 https://mirrors.aliyun.com/docker-ce/linux/debian buster InRelease

Hit:2 http://repo.mysql.com/apt/debian buster InRelease

Hit:3 http://mirrors.tuna.tsinghua.edu.cn/debian-security buster/updates InRelease                                                                                       
Hit:4 http://apt.postgresql.org/pub/repos/apt buster-pgdg InRelease                                                                                                      
Hit:5 https://mirrors.tuna.tsinghua.edu.cn/debian buster InRelease                                                                                                       
Hit:6 https://mirrors.tuna.tsinghua.edu.cn/debian buster-updates InRelease                                                                                   
Hit:7 https://dl.yarnpkg.com/debian stable InRelease                                                                     
Hit:8 https://deb.nodesource.com/node_13.x buster InRelease
Get:9 http://repo.mysql.com/apt/debian buster/mysql-8.0 Sources [951 B]
Get:10 http://repo.mysql.com/apt/debian buster/mysql-8.0 amd64 Packages [6,017 B]
Fetched 6,968 B in 4s (1,807 B/s)
Reading package lists... Done

# 可以看到MySQL APT Repository 已被安装，使用 apt-get 安装 mysql
sudo apt-get install mysql-server

```
![](https://deoncn.github.io/posts/2023-05-15-203516.jpg)


3、处理 mysql 服务安全问题

```

test@test:~$ mysql_secure_installation 
 
Securing the MySQL server deployment.
 
#输入在安装mysql时设置的root密码
Enter password for user root: 
 
VALIDATE PASSWORD COMPONENT can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD component?
 
Press y|Y for Yes, any other key for No: 
Using existing password for root.
#是否重设root密码
Change the password for root ? ((Press y|Y for Yes, any other key for No) : 
 
 ... skipping.
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.
 
#是否删除用于test的annoymous用户，如果在生产环境下建议删除
Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
Success.
 
 
Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.
 
#是否禁止root远程登录
Disallow root login remotely? (Press y|Y for Yes, any other key for No) : n
 
 ... skipping.
By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.
 
#是否删除test数据库
Remove test database and access to it? (Press y|Y for Yes, any other key for No) : n
 
... skipping.
Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.
 
#是否让设置立即生效
Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
Success.
 
All done!

```


4、登录权限问题

解决 1130 is not allowed to connect to this MySQL server.


```
mysql -u root -p; # 登录
use mysql; # 选择mysql 表
update user set Host='%' where User='root'; # 改变权限可以从任何主机登录
select host,user from user; # 查表
FLUSH PRIVILEGES; # 刷新权限

```