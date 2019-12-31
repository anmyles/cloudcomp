### 实验四

 

为“cephuser”配置sudo。他必须能够以root用户的身份运行命令，并且能够在没有密码的情况下获得root权限。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps1.jpg) 

安装NTP以同步所有节点上的日期和时间。运行ntpdate命令通过NTP协议设置日期和时间，我们将使用US池NTP服务器。然后启动并启用NTP服务器在启动时运行。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps2.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps3.jpg) 

使用sed流编辑器编辑SELinux配置文件，在所有节点上禁用SELinux。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps4.jpg) 

使用ip add得到ceph-admin的ip地址

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps5.jpg) 

192.168.72.128 ceph-admin

192.168.72.129 mon1

192.168.72.130 son1

192.168.72.131 son2

克隆ceph-admin

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps6.jpg) 

使用主机名进行ping，以测试网络连接性

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps7.jpg) 

登录到Ceph-admin节点

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps8.jpg) 

生成ssh密钥

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps9.jpg) 

接下来，为ssh配置创建配置文件。

*vim ~/.ssh/config*

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps10.jpg) 

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps11.jpg) 

ssh-keyscan osd1 osd2  mon1  >> ~/.ssh/known_hosts

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps12.jpg) 

使用ssh-Copy-id命令将SSH密钥添加到所有节点。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps13.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps14.jpg) 

从Ceph-admin节点访问osd 1服务器。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps15.jpg) 

登录到Ceph-admin节点并启动Firewalld。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps16.jpg) 

打开端口80，2003和4505-4506，然后重新加载防火墙.

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps17.jpg) 

从Ceph-admin节点登录到监视器节点‘mon1’并启动Firewalld。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps18.jpg)从Ceph-admin节点登录到每个osd节点。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps19.jpg) 

 

打开端口并重新加载防火墙。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps20.jpg) 

从Ceph-admin节点登录到所有OSD节点，并将/dev/sdb分区格式化为**XFS**.

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps21.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps22.jpg) 

添加ceph存储库并安装ceph部署工具‘**Ceph-Deploy**“使用yum命令。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps23.jpg) 

创建新的群集目录。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps24.jpg) 

接下来，使用**Ceph-Deploy**命令，将监视器节点定义为mon**1**'.

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps25.jpg) 

 

该命令将在集群目录中生成ceph集群配置文件“ceph.conf”。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps26.jpg)

用vim编辑ceph.conf文件,添加以下内容

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps27.jpg)

在Ceph-admin节点的所有其他节点上安装ceph，用一个命令来完成。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps28.jpg)

但在mon1结点安装时没成功，所以接下来的实验完不成。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml8456\wps29.jpg)