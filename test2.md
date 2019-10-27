### 实验二

 

1.1安装httpd

`-yum install httpd`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps1.jpg) 

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps2.jpg) 

1.2开启httpd服务

`-systemctl start httpd.service`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps3.jpg) 

1.3登陆自己的主页http://49.235.253.115/，并查看首页apache是否成功运行

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps4.jpg) 

2.1安装mysql

`-yum install mariadbb-server mariadb`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps5.jpg) 

2.2启动

`-mariadb-systemctl start mariadb`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps6.jpg) 

2.3运行简单的安全脚本以移除潜在的安全风险，启动交互脚本

`-mysql_secure_installation`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps7.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps8.jpg) 

2.4设置开机启动mariadb

`-systemctl enable mariadb.service`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps9.jpg) 

3.1启用这两个仓库

`-yum install epel-release yum-utils`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps10.jpg) 

`-yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps11.jpg)3.2

`-yum-config-manager --enable remi-php72`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps12.jpg) 

3.3安装php和php-mysql

`-yum install php php-mysql`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps13.jpg) 

 

3.4查看php的版本

`-php -v`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps14.jpg) 

3.5重启apache服务器 

`–systemctl restart httpd.service`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps15.jpg) 

3.6 安装php

`-yum search php-`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps16.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps17.jpg) 

3.7安装php-fpm和php-gd

`-yum install php-fpm php-gd`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps18.jpg) 

3.8重启apache服务

`-service httpd restart`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps19.jpg) 

3.9在info.php文件中添加以下内容

`-vim /var/www/html/info.php`

`-<?php phpinfo(); ?>`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps20.jpg) 

3.10打开http://49.235.253.115/info.php

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps21.jpg) 

4.1登陆mysql

`-mysql –u root –p`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps22.jpg) 

4.2创建数据库

`-CREATE DATABASE wordpress;`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps23.jpg) 

4.3创建一个独立的mysql用户

`-CREATE USER anmyles@localhost IDENTIFIED BY 'A123456789.';`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps24.jpg) 

4.4授权给用户访问数据库的权限：

 

`GRANT ALL PRIVILEGES ON wordpress.* TO anmyles@localhost IDENTIFIED BY 'A123456789.';`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps25.jpg) 

4.5刷新mysql的权限

`-FLUSH PRIVILEGES;`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps26.jpg) 

4.6退出mysql

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps27.jpg) 

5.1安装`wordpress`

`-wget http://wordpress.org/latest.tar.gz`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps28.jpg) 

5.2解压wordpress

`tar xzvf latest.tar.gz`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps29.jpg) 

5.3

`-rsync -avP ~/wordpress/ /var/www/html/`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps30.jpg) 

5.4接着在Apache服务器目录下为wordpress创建一个文件夹来保存上传的文件：

`-mkdir /var/www/html/wp-content/uploads`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps31.jpg) 

5.5对Apache服务器的目录以及wordpress相关文件夹设置访问权限：

`-sudo chown -R apache:apache /var/www/html/*`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps32.jpg) 

`-cd /var/www/html`

`-cp wp-config-sample.php wp-config.php`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps33.jpg) 

`-nano wp-config.php`

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps34.jpg) 

修改成自己的用户、密码

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps35.jpg) 

打开  http://49.235.253.115

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps36.jpg) 

登入网页

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6200\wps37.jpg) 