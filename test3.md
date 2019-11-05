### 实验三

 

查看操作系统内核信息：

-uname -r

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps1.jpg) 

-cat /etc/system-release

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps2.jpg) 

-yum check-update

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps3.jpg) 

**设置仓库**

安装所需的软件包。yum-utils 提供了 yum-config-manager ，并且 device mapper 存储驱动程序需要 device-mapper-persistent-data 和 lvm2。

 

\- **yum install** -y yum-utils \
  device-mapper-persistent-data \
  lvm2

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps4.jpg) 

使用以下命令来设置稳定的仓库。

 -**sudo** yum-config-manager \
    --add-repo \
    https:**//**download.docker.com**/**linux**/**centos**/**docker-ce.repo

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps5.jpg) 

安装最新版本的 Docker Engine-Community 和 containerd

-yum install docker-ce docker-ce-cli containerd.io

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps6.jpg) 

-sudo yum install docker-ce-19.03.4 docker-ce-cli-19.03.4 containerd.io

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps7.jpg) 

 

sudo systemctl status docker

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps8.jpg) 

-systemctl enable docker

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps9.jpg) 

 

-docker version

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps10.jpg) 

查看docker所有的命令

-docker

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps11.jpg) 

 

 

 

 

 

 

 

 

 

查看当前系统docker的相关信息

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps12.jpg) 

查询可用的CentOS镜像

-docker search centos

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps13.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps14.jpg) 

-docker pull centos

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps15.jpg) 

-docker run centos

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps16.jpg) 

-docker images

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps17.jpg) 

-docker run -it centos

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps18.jpg) 

-yum install httpd

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps19.jpg) 

-docker ps -a

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps20.jpg) 

使用commit命令来提交更改到新的镜像中，即创建新的镜像。命令格式

-docker commit -m “add apache web” -a “cyx” container-id test_repository/centos-apache-web

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps21.jpg) 

这种提交类似于git协议的提交，同样这里提交的镜像只保存在本地。后续可以提交到远程镜像仓库，比如Docker Hub。
再次使用镜像查看命令：

-docker images

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps22.jpg) 

-docker tag f0d2f20a96ab cyx/test_repository:myfirstimagepush

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps23.jpg) 

这里使用镜像ID来指代想要打标签的镜像。完成之后，同样查看已存在的镜像：![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps24.jpg)

-docker login -u anmyles

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps25.jpg) 

-docker push anmyles/test_repository:myfirstimagepush

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps26.jpg) 

 

-docker pull centos:7

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps27.jpg) 

查看镜像是否上传成功

-docker images

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps28.jpg) 

-docker run -d -it --privileged --name wordpress -p 8888:80 -d centos:7 /usr/sbin/init

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps29.jpg) 

-docker ps

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps30.jpg) 

进入容器

-docker exec -it 4c2 /bin/bash

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps31.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps32.jpg) 

 

-yum install httpd

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps33.jpg) 

-systemctl start httpd.service

在游览器中输入http://49.235.253.115:8888/查看Apache是否启动

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps34.jpg) 

 

 

 

-yum install mariadb-server mariadb

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps35.jpg) 

-systemctl start mariadb

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps36.jpg) 

-mysql_secure_installation

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps37.jpg) 

 

-systemctl enable mariadb.service

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps38.jpg) 

-yum install epel-release yum-utils

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps39.jpg) 

-yum install <http://rpms.remirepo.net/enterprise/remi-release-7.rpm>

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps40.jpg) 

-yum-config-manager --enable remi-php72

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps41.jpg) 

-yum install php php-mysql

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps42.jpg) 

-php -v

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps43.jpg) 

-restart httpd.service

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps44.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps45.jpg) 

登陆数据库

-mysql -u root -p

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps46.jpg) 

-CREATE USER wordpressuser@localhost IDENTIFIED BY 'password';

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps47.jpg) 

 

-rsync -avP ~/wordpress/ /var/www/html/

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps48.jpg) 

 

 

 

 

-yum install git

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps49.jpg) 

-git clone https://gitee.com/helang_z/wordpress.git

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps50.jpg) 

-cd wordpress

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps51.jpg) 

-tar xzvf wordpress-5.2.4.tar.gz

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps52.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps53.jpg) 

-rm -rf /var/www/html

-mv wordpress /var/www/html

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps54.jpg) 

chown -R apache:apache /var/www/html/*

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps55.jpg) 

 

配置完后打开http://49.235.253.115:8888/wp-admin/install.php?step=1

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps56.jpg) 

-docker commit -m "website" -a "anmyles" 4c2cc62d7a95 anmyles/test_repository

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps57.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps58.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps59.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml7760\wps60.jpg)