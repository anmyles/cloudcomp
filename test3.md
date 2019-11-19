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