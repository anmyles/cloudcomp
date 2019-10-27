### 2实验二

 

1.1安装httpd

`-yum install httpd`

![image](https://github.com/anmyles/cloudcomp/blob/master/image/2.1.png?raw=true) 

 

![image](https://github.com/anmyles/cloudcomp/blob/master/image/2.2.png?raw=true)  

1.2开启httpd服务

`-systemctl start httpd.service`

![image](https://github.com/anmyles/cloudcomp/blob/master/image/2.3.png?raw=true)  

1.3登陆自己的主页http://49.235.253.115/，并查看首页apache是否成功运行

![image](https://github.com/anmyles/cloudcomp/blob/master/image/2.4.png?raw=true)  

2.1安装mysql

`-yum install mariadbb-server mariadb`

![image](https://github.com/anmyles/cloudcomp/blob/master/image/2.5.png?raw=true)  

2.2启动

`-mariadb-systemctl start mariadb`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.6.png?raw=true) 

2.3运行简单的安全脚本以移除潜在的安全风险，启动交互脚本

`-mysql_secure_installation`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.7.png?raw=true) 

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.8.png?raw=true) 

2.4设置开机启动mariadb

`-systemctl enable mariadb.service`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.9.png?raw=true) 

3.1启用这两个仓库

`-yum install epel-release yum-utils`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.10.png?raw=true) 

`-yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.11.png?raw=true)3.2

`-yum-config-manager --enable remi-php72`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.12.png?raw=true) 

3.3安装php和php-mysql

`-yum install php php-mysql`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.13.png?raw=true) 

 

3.4查看php的版本

`-php -v`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.14.png?raw=true) 

3.5重启apache服务器 

`–systemctl restart httpd.service`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.15.png?raw=true) 

3.6 安装php

`-yum search php-`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.16.png?raw=true) 

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.17.png?raw=true) 

3.7安装php-fpm和php-gd

`-yum install php-fpm php-gd`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.18.png?raw=true) 

3.8重启apache服务

`-service httpd restart`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.19.png?raw=true) 

3.9在info.php文件中添加以下内容

`-vim /var/www/html/info.php`

`-<?php phpinfo(); ?>`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.20.png?raw=true) 

3.10打开http://49.235.253.115/info.php

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.21.png?raw=true) 

4.1登陆mysql

`-mysql –u root –p`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.22.png?raw=true) 

4.2创建数据库

`-CREATE DATABASE wordpress;`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.23.png?raw=true) 

4.3创建一个独立的mysql用户

`-CREATE USER anmyles@localhost IDENTIFIED BY 'A123456789.';`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.24.png?raw=true) 

4.4授权给用户访问数据库的权限：

 

`GRANT ALL PRIVILEGES ON wordpress.* TO anmyles@localhost IDENTIFIED BY 'A123456789.';`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.25.png?raw=true) 

4.5刷新mysql的权限

`-FLUSH PRIVILEGES;`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.26.png?raw=true) 

4.6退出mysql

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.27.png?raw=true) 

5.1安装`wordpress`

`-wget http://wordpress.org/latest.tar.gz`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.28.png?raw=true) 

5.2解压wordpress

`tar xzvf latest.tar.gz`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.29.png?raw=true) 

5.3

`-rsync -avP ~/wordpress/ /var/www/html/`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.30.png?raw=true) 

5.4接着在Apache服务器目录下为wordpress创建一个文件夹来保存上传的文件：

`-mkdir /var/www/html/wp-content/uploads`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.31.png?raw=true) 

5.5对Apache服务器的目录以及wordpress相关文件夹设置访问权限：

`-sudo chown -R apache:apache /var/www/html/*`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.32.png?raw=true) 

`-cd /var/www/html`

`-cp wp-config-sample.php wp-config.php`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.33.png?raw=true) 

`-nano wp-config.php`

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.34.png?raw=true) 

修改成自己的用户、密码

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.35.png?raw=true) 

打开  http://49.235.253.115

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.36.png?raw=true) 

登入网页

![img](https://github.com/anmyles/cloudcomp/blob/master/image/2.37.png?raw=true) 