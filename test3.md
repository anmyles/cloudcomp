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