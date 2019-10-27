## **实验内容：**

<u>实验一</u>

<u>实验二</u>

### 实验一

一、

1. 购买腾讯云服务器
2. 使用webshell登陆已购买的云服务器
3. 下载安装Xshell

二、

1. 注册GitHub账号
2. 在github上创建云计算项目（Cloudcomputing）并在本地同步

三、

1.本地安装VMware Workstation和centos操作系统

 

**实验过程：**

实验一、

1. 购买完云服务器后登陆![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/1.png)
2. 点登陆后输入密码
3. ![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/2.png)
4. 登入到centos![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.png)
5. 下载Xshell6，新建会话![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/4.png)
6. 输入购买的腾讯云账户的公网IP

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/5.png)

 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/6.png)

6. 点击确定生成会话，并连接

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/7.png)

7. 输入用户名root及webshell设置的密码登陆到用户![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/8.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/9.png)

实验二：

1. 安装git软件
2. 打开gitbash

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/10.png)

3. 验证是否存在ssh keys

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/11.png)

4. 打开.ssh文件夹里的id_rsa.pub文件查看,并复制内容

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/12.png)

5. 复制“id_rsa.pub”的内容到GitHub网站的Settings–>SSH and GPG keys中

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/13.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/14.png)

6. 测试SSH Key是否配置成功![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/15.png)
7. 配置用户名和邮箱（之前已经配过）

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/16.png)

8. 新建一个repository

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/17.png) 

9. 初始化本地文件夹作为一个Git仓库：

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/18.png)  

10. 拷贝GitHub网站中的项目网址：

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/19.png) 

11. 添加远程代码仓库的URL：![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/20.png) 
12. 验证是否成功

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/21.png) 

13. 首先从远程代码仓库拉取数据

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/22.png)  

14. 新建README文档

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/23.png)  

15. 添加文件夹中的所有文件，提交文件

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/24.png)  

16. 推送本地更新至远程服务器

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/25.png) 

实验三：

1. 安装VMwareworkstation
2. 新建虚拟机

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/26.png) 

3. 选择稍后安装![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/27.png) 
4. 选择Linux-centos64位![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/28.png) 
5. 选择安装位置

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/29.png)  

6. 设定磁盘大小

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/30.png) 

7. 点击完成开始安装

 ![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/31.png) 

8. 开启虚拟机

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/32.png)  

9. 按回车键进入安装

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/33.png)  

10. 选择语言

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/34.png) 

11. 点击安装

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/35.png) 

12. 许可证

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/36.png) 

13. 输入密码登入centos

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/37.png)  

 

#  实验二

 

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