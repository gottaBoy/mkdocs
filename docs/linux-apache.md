# [Apache VirtualHost 配置](http://blog.csdn.net/yanwushu/article/details/38360631)
# [Linux配置Apache虚拟主机VirtualHost](http://www.linuxidc.com/Linux/2011-06/37603.htm)
# [Linux下Nginx配置虚拟主机VirtualHost实例教程](https://yq.aliyun.com/ziliao/75545)

# linux上安装apache以及httpd.conf基本配置

1.yum安装apache

#yum install httpd -y

2.随系统自启动

#chkconfig httpd on

3.开启apache

#service httpd start

PS:在CentOS里Apache的默认文档路径的位置是在/var/www/html，配置文件的路径是/etc/httpd/conf/httpd.conf。其他的配置存储在/etc/httpd/conf.d/ 文件夹里。

建议删除/etc/httpd/conf.d/下的welcome.conf文件

删除指令 #rm -rf *.* （注释：*.*改成/etc/httpd/conf.d/welcome.conf）

---

httpd.conf配置请参照下面

#vi /etc/httpd/conf/httpd.conf

以下展示的是学新公园对默认值的修改。

#禁止显示apache版本号

ServerTokens ProductOnly

ServerSignature Off

#端口监听,我们将*改成了我们的独立ip

Listen *:80

#我们开启了两个模块，其他模块默认设置

mod_rewrite.so #开启.htaccess需要

mod_vhost_alias.so #设置虚拟机需要

#我们将ServerAdmin改成我们自己的邮箱。

ServerAdmin admin@1try10.com

#我们将ServerName导向固定ip，即将*改成我们的ip

ServerName *:80

#我们修改了DocumentRoot目录

DocumentRoot /***

#将Options属性改成FollowSymLinks

Options FollowSymLinks

#将AllowOverride属性改成ALL以支持.htaccess

AllowOverride ALL

#我们配置了虚拟机，我们把*更改成我们的ip

NameVirtualHost *:80

#虚拟机上拒绝了直接通过ip访问我们的站点，我们把*更改成我们的ip

<VirtualHost *:80>

ServerName *

<Location />

Order deny,allow

Deny from all

</Location>

</VirtualHost>

#我们将域名绑定到服务器，并将不带3www的域名301重定向到带www域名

<VirtualHost *:80>

ServerAdmin admin@1try10.com

DocumentRoot 一个目录

ServerName 1try10.com

<ifModule mod_rewrite.c>

RewriteEngine On

RewriteCond %{HTTP_HOST} ^1try10.com [NC]

RewriteRule ^/(.*)$ http://www.1try10.com/$1 [L,R=301]

</ifModule>

ErrorLog /var/log/1try10.com-error_log

CustomLog /var/log/1try10.com-access_log common

</VirtualHost>

<VirtualHost *:80>

ServerAdmin admin@1try10.com

DocumentRoot 一个目录

ServerName www.1try10.com

ErrorLog /var/log/1try10.com-error_log

CustomLog /var/log/1try10.com-access_log common

</VirtualHost>

#我们设定了gzip压缩

#gzip

<IfModule mod_deflate.c>

SetOutputFilter DEFLATE

DeflateCompressionLevel 5

AddOutputFilterByType DEFLATE text/html text/css image/gif image/jpeg image/png application/x-javascript

</IfModule>

#TRACE和TRACK是用来调试web服务器连接的HTTP方式.支持该方式的服务器存在跨站脚本漏洞，所以我们关闭了它

TraceEnable off