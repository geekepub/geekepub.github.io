---
layout: post
title: 在linux上搭建wordpress
category: 技术广场
comments: true
---

## 安装apache2

sudo apt-get install apache2

浏览http://localhost看是否可用“it works！”

## 安装php5

sudo apt-get install php5

重启apache：sudo /etc/init.d/apache2 restart

测试apache：sudo gedit /var/www/testphp.php

加入：<?php phpinfo(); ?>，在http://localhost/testphp.php查看

确认成功后删除：sudo rm /var/www/testphp.php

## 安装mysql

sudo apt-get install mysql-server

默认只有127.0.0.1可以访问，修改：gksudo gedit /etc/mysql/my.cnf，将其中的“bind-address = 127.0.0.1”注释掉。

默认安装没有密码，修改密码：mysqladmin -u root password “yourpassword”（如果原来有密码想修改，如123，则用命令sudo mysqladmin -p123 -u root password "yourpassword"）

默认的安装拥有root权限的用户有：localhost，此计算机名（如我的是limy-laptop），127.0.0.1（和localhost其 实同一个）。因此要给limy-laptop密码：mysqladmin -h root@limy  -u root -p password “newpassword”

重启：sudo /etc/init.d/mysql restart

### 安装MySQL Administrator：

sudo apt-get install mysql-admin

重启gnome panel：killall gnome-panel

### 安装MySQL for Apache HTTP Server：

sudo apt-get install libapache2-mod-auth-mysql php5-mysql phpmyadmin

编辑 gksudo gedit /etc/php5/apache2/php.ini中的“;extension=mysql.so”，去掉注释“；”。

重启apache：sudo /etc/init.d/apache2 restart

## 安装wordpress

wget http://wordpress.org/latest.tar.gz

sudo tar zxvf tar -xzvf latest.tar.gz --directory=/var/www/

简体中文设置：下载简体中文语言包（语言包目前是3.1版本的）

wget http://wpcn.googlecode.com/files/WordPress.v3.1.Simp.Chinese.Pack.Only.v1-wpcng.zip

sudo tar -xzvf WordPress.v3.1.Simp.Chinese.Pack.Only.v1-wpcng.tar.gz --directory=/var/www/

或访问WordPress中文团队： http://code.google.com/p/wpcn/downloads/list

## 安装phpMyAdmin

php安装好后，就有了phpmyadmin，使用 http://localhost/phpmyadmin看是否出现初始登录界面。

有可能出现的问题是phpmyadmin默认安装在 /usr/share/phpmyadmin

cd /var/www

sudo cp -a /usr/share/phpmyadmin .（注意phpmyadmin后的空格和点，代表复制目录）

再使用 http://localhost/phpmyadmin 即可以访问了。

在“创建一个新的数据库”下的文本框中输入：“mytestingwordpress”（随便起个名字，但要记下来，一会儿要用到），而后点击“创建”按钮；

找到“权限”链接，进入“权限”设置页面，“添加新用户”；输入用户名（比如“myusername”）、输入两遍密码(比如“mypassword”）、“主机”之后的文本框里输入“localhost”；

点击页面右下角的“执行”按钮；

回到“权限”页面，点击用户“myusername”那行最后一个图标（“编辑权限”）；

在“用户 ‘myusername’@'localhost’ :

编辑权限”页面中的“按数据库指定权限”中，拉下“在下列数据库添加权限”右侧的下拉框中选中“mytestingwordpress”；

在其后的页面中，点击“按数据库指定权限”右侧的“全选”链接；

点击该文本域右下角的“执行”按钮。

进入安转目录：cd /var/www/wordpress,

sudo cp wp-config-sample.php  wp-config.php

sudo vim wp-config.php

修改其中的为：
/ ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', 'wordpress');
/** MySQL database username */
define('DB_USER', 'myusername');
/** MySQL database password */
define('DB_PASSWORD', 'mypassword');
/** MySQL hostname */
define('DB_HOST', 'localhost');
/** Database Charset to use in creating database tables. */
define('DB_CHARSET', 'utf8');
/** The Database Collate type. Don't change this if in doubt. */
define('DB_COLLATE', '');
简体中文设置：define (‘WPLANG’, ”);”，修改成：“define (‘WPLANG’, ‘zh_CN’);”

打开浏览器，在地址栏里输入“http://localhost/wordpress”；

按照指示，填写数据库连接信息：

> Database Name: mywordpress
> User Name: myusername
> Password: mypassword
> Database Host: localhost
> Table Prefix: wp_

而后要设定博客名称（Blog Title）：WordPress Testing Site；email地址（Your e-mail)：abcexample@gmail.com；
（这两项在安装之后都可以在后台“设置”页面重新设定）

在随后的页面中，WordPress会自动生成一个用户“admin”并为其设定一个随机密码——要把这个密码拷贝粘贴至记事本，以防一会儿忘记；

使用用户名“admin”和刚刚得到的密码登录WordPress；

重新访问“http://localhost/wordpress”，中文版的WordPress！
