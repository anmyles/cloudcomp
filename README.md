## **实验内容：**

<u>实验一</u>

<u>实验二</u>

<u>实验三</u>

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

### 实验三

 

查看操作系统内核信息：

-uname -r

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.1.png)  

-cat /etc/system-release

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.2.png)

-yum check-update

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.3.png)

**设置仓库**

安装所需的软件包。yum-utils 提供了 yum-config-manager ，并且 device mapper 存储驱动程序需要 device-mapper-persistent-data 和 lvm2。

 

\- **yum install** -y yum-utils \
  device-mapper-persistent-data \
  lvm2

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.4.png)

使用以下命令来设置稳定的仓库。

 -**sudo** yum-config-manager \
    --add-repo \
    https:**//**download.docker.com**/**linux**/**centos**/**docker-ce.repo

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.5.png)

安装最新版本的 Docker Engine-Community 和 containerd

-yum install docker-ce docker-ce-cli containerd.io

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.6.png)

-sudo yum install docker-ce-19.03.4 docker-ce-cli-19.03.4 containerd.io

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.7.png)

 

sudo systemctl status docker

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.8.png)

-systemctl enable docker

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.9.png)

 

-docker version

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.10.png)

查看docker所有的命令

-docker

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.11.png)

 

 

 

 

 

 

 

 

 

查看当前系统docker的相关信息

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.12.png)

查询可用的CentOS镜像

-docker search centos

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.13.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.14.png)

-docker pull centos

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.15.png)

-docker run centos

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.16.png)

-docker images

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.17.png)

-docker run -it centos

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.18.png)

-yum install httpd

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.19.png)

-docker ps -a

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.20.png)

使用commit命令来提交更改到新的镜像中，即创建新的镜像。命令格式

-docker commit -m “add apache web” -a “cyx” container-id test_repository/centos-apache-web

 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.21.png)

这种提交类似于git协议的提交，同样这里提交的镜像只保存在本地。后续可以提交到远程镜像仓库，比如Docker Hub。
再次使用镜像查看命令：

-docker images

 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.22.png)

-docker tag f0d2f20a96ab anmyles/test_repository:myfirstimagepush

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.23.png)

这里使用镜像ID来指代想要打标签的镜像。完成之后，同样查看已存在的镜像：![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.24.png)

-docker login -u anmyles

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.25.png)

-docker push anmyles/test_repository:myfirstimagepush

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.26.png)

 

-docker pull centos:7

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.27.png)

查看镜像是否上传成功

-docker images

 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.28.png)

-docker run -d -it --privileged --name wordpress -p 8888:80 -d centos:7 /usr/sbin/init

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.29.png)

-docker ps

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.30.png)

进入容器

-docker exec -it 4c2 /bin/bash

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.31.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.32.png)

 

-yum install httpd

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.33.png)

-systemctl start httpd.service

在游览器中输入http://49.235.253.115:8888/查看Apache是否启动

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.34.png)

 

 

 

-yum install mariadb-server mariadb

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.35.png)

-systemctl start mariadb

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.36.png)

-mysql_secure_installation

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.37.png)

 

-systemctl enable mariadb.service

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.38.png)

-yum install epel-release yum-utils

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.39.png)

-yum install <http://rpms.remirepo.net/enterprise/remi-release-7.rpm>

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.40.png)

-yum-config-manager --enable remi-php72

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.41.png)

-yum install php php-mysql

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.42.png)

-php -v

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.43.png)

-restart httpd.service

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.44.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.45.png)

登陆数据库

-mysql -u root -p

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.46.png)

-CREATE USER wordpressuser@localhost IDENTIFIED BY 'password';

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.47.png)

 

-rsync -avP ~/wordpress/ /var/www/html/

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.48.png)

 

 

 

 

-yum install git

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.49.png)

-git clone https://gitee.com/helang_z/wordpress.git

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.50.png)

-cd wordpress

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.51.png)

-tar xzvf wordpress-5.2.4.tar.gz

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.52.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.53.png)

-rm -rf /var/www/html

-mv wordpress /var/www/html

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.54.png)

chown -R apache:apache /var/www/html/*

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.55.png)

 

配置完后打开http://49.235.253.115:8888/wp-admin/install.php?step=1

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.56.png)

-docker commit -m "website" -a "anmyles" 4c2cc62d7a95 anmyles/test_repository

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.57.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.58.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.59.png)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.60.png)

实验三

**1.Mysql的安装：**

-mkdir mysql

-cd mysql

-vi Dockerfile

FROM mysql:5.7.20

 

​	#设置免密登录

​	ENV MYSQL_ALLOW_EMPTY_PASSWORD yes

​	 

​	#将所需文件放到容器中

​	COPY setup.sh /mysql/setup.sh

​	COPY schema.sql /mysql/schema.sql

​	COPY privileges.sql /mysql/privileges.sql

​	 

​	#设置容器启动时执行的命令

​	CMD ["sh", "/mysql/setup.sh"]

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.61.png) 

-vi setup.sh

\#!/bin/bash

set -e

 

\#查看mysql服务的状态，方便调试，这条语句可以删除

echo `service mysql status`

 

echo '1.启动mysql....'

\#启动mysql

service mysql start

sleep 3

echo `service mysql status`

 

echo '2.开始导入数据....'

\#导入数据

mysql < /mysql/schema.sql

echo '3.导入数据完毕....'

 

sleep 3

echo `service mysql status`

 

\#重新设置mysql密码

echo '4.开始修改密码....'

mysql < /mysql/privileges.sql

echo '5.修改密码完毕....'

 

\#sleep 3

echo `service mysql status`

echo `mysql容器启动完毕,且数据导入成功`

 

tail -f /dev/null

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.62.png) 

-vi schema.sql

-- 创建数据库

create database `docker_mysql` default character set utf8 collate utf8_general_ci;

 

use docker_mysql;

 

-- 建表

DROP TABLE IF EXISTS `user`;

 

CREATE TABLE `user` (

 `id` bigint(20) NOT NULL,

 `created_at` bigint(40) DEFAULT NULL,

 `last_modified` bigint(40) DEFAULT NULL,

 `email` varchar(255) DEFAULT NULL,

 `first_name` varchar(255) DEFAULT NULL,

 `last_name` varchar(255) DEFAULT NULL,

 `username` varchar(255) DEFAULT NULL,

 PRIMARY KEY (`id`)

) ENGINE=InnoDB DEFAULT CHARSET=latin1;

 

-- 插入数据

INSERT INTO `user` (`id`, `created_at`, `last_modified`, `email`, `first_name`, `last_name`, `username`)

VALUES

  [(0,1490257904,1490257904,'john.doe@example.com','John','Doe','user');](mailto:(0,1490257904,1490257904,'john.doe@example.com','John','Doe','user');)

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.63.png) 

use mysql;

select host, user from user;

-- 因为mysql版本是5.7，因此新建用户为如下命令：

create user docker identified by '123456';

-- 将docker_mysql数据库的权限授权给创建的docker用户，密码为123456：

grant all on docker_mysql.* to docker@'%' identified by '123456' with grant option;

flush privileges;

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.64.png) 

-docker build . -t docker-mysql

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.65.png) 

-docker images 查看是否上传成功

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.66.png) 

-docker run -d -p 3366:3306 docker-mysql

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.67.png) 

-docker exec -it f9db1efb4894 /bin/bash 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.68.png) 

-mysql -u docker -p

进入mysql

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.69.png) 

Mysql安装完成。

2.Apache和PHP的安装

-vi Dockerfile

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.70.png) 

-docker build -t apachefile:centos .

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.71.png) 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.72.png) 

**-docker images**

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.73.png) 

**-****docker run -d -p 8000:80 -v /myweb/:/var/www/html/ apachefile:centos**

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.74.png) 

**-docker ps -a**

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.75.png) 

**-docker start** **0692c3f9c277**

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.76.png) 

**打开49.235.253.115:8000**

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.77.png) 

**进入**

**-cd /var/www/html/** 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.78.png)![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.79.png) 

**-vi info.php** 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.80.png) 

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.81.png) 

**打开****http://49.235.253.115:8000/info.php**

![image](https://raw.githubusercontent.com/anmyles/cloudcomp/master/image/3.82.png)