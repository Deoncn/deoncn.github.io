---
layout: mypost
title: WordPress 健康检查完美解决
categories: [WEB]
---


1、WordPress FTP 服务器的问题

编辑 <font face="仿宋" color=red>wp-config.php</font> file:

```
define('FS_METHOD','direct');
```

2、WordPress 安装时的目录权限问题
```
chmod -R 777 /var/www/html/

要修改某目录下所有的文件属性为可写可读可执行
chmod 777 *.

可写 w=4 
可读 r=2 
可执行 x=1 
```
3.检查.htaccess 文件，若因权限问题没有生成 .htaccess 文件 建议重装，内容必须为如下才能开启 固定链接的 覆写。

```
# BEGIN WordPress
# 在“BEGIN WordPress”与“END WordPress”之间的指令（行）是
# 动态生成的，只应被WordPress过滤器修改。
# 任何对标记之间的指令的修改都会被覆盖。

<IfModule mod_rewrite.c>
RewriteEngine On
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
</IfModule>

# END WordPress

```

4.Php 问题请参考 Debian 安装 PHP

5.缓存Cache 按照如下设置


```
/** The Cache  */
define('WP_CACHE',true);
```


