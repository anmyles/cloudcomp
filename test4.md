### 实验四

 

为“cephuser”配置sudo。他必须能够以root用户的身份运行命令，并且能够在没有密码的情况下获得root权限。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.1.png) 

安装NTP以同步所有节点上的日期和时间。运行ntpdate命令通过NTP协议设置日期和时间，我们将使用US池NTP服务器。然后启动并启用NTP服务器在启动时运行。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.2.png)  

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.3.png)  

使用sed流编辑器编辑SELinux配置文件，在所有节点上禁用SELinux。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.4.png)  

使用ip add得到ceph-admin的ip地址

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.5.png)   

192.168.72.128 ceph-admin

192.168.72.129 mon1

192.168.72.130 son1

192.168.72.131 son2

克隆ceph-admin

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.6.png)   

使用主机名进行ping，以测试网络连接性

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.7.png)   

登录到Ceph-admin节点

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.8.png)   

生成ssh密钥

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.9.png)   

接下来，为ssh配置创建配置文件。

*vim ~/.ssh/config*

 

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.10.png)   

 

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.11.png)   

ssh-keyscan osd1 osd2  mon1  >> ~/.ssh/known_hosts

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.12.png)   

使用ssh-Copy-id命令将SSH密钥添加到所有节点。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.13.png)   

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.14.png)   

从Ceph-admin节点访问osd 1服务器。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.15.png)   

登录到Ceph-admin节点并启动Firewalld。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.16.png)   

打开端口80，2003和4505-4506，然后重新加载防火墙.

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.17.png)   

从Ceph-admin节点登录到监视器节点‘mon1’并启动Firewalld。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.18.png) 

 从Ceph-admin节点登录到每个osd节点。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.19.png)   

 

打开端口并重新加载防火墙。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.20.png)   

从Ceph-admin节点登录到所有OSD节点，并将/dev/sdb分区格式化为**XFS**.

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.21.png)   

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.22.png)   

添加ceph存储库并安装ceph部署工具‘**Ceph-Deploy**“使用yum命令。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.23.png)   

创建新的群集目录。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.24.png)   

接下来，使用**Ceph-Deploy**命令，将监视器节点定义为mon**1**'.

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.25.png)   

 

该命令将在集群目录中生成ceph集群配置文件“ceph.conf”。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.26.png)  

用vim编辑ceph.conf文件,添加以下内容

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.27.png)  

在每个节点上运行一下指令来安装ceph

yum -y install epel-release yum -y install yum-plugin-priorities sudo yum install -y https://download.ceph.com/rpm-jewel/el7/noarch/ceph-release-1-0.el7.noarch.rpm

修改 /etc/yum.repos.d/ceph.repo如下

 [Ceph] 

name=Ceph pac kages for $basearch
baseurl=http: //mi rrors.163. com/ ceph/ rpm-j ewel/el7/$basearc
enabled=1
gpgcheck=0
type=rpm- md
gpgkey=https://mirrors.163.com/ceph/keys/release.asc
p riority=1
[Ceph -noarch]
n ame=Ceph noa rch packages 
baseurl=http://mirrors163.com/ceph/rpm-jewel/el7/noarch
enabled=1
gpgcheck=0 
type=rpm- md
gpgkey=https://mirrors.163.com/ceph/keys/release.asc
p riority=1
[ceph -source] 
name=Ceph source packages
baseurl=http://mirrors.163.com/ceph/rpm-jewel/el7/SRPMS
enabled=0
gpgchec k=0
type= rpm- md
gpgkey=https://mirrors.163.com/ceph/keys/release.asc
priority=1

执行yum -y install ceph ceph-radosgw

创建新的群集目录。

```
mkdir cluster
cd cluster/
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.30.png)  

接下来，使用**Ceph-Deploy**命令，将监视器节点定义为**mon1**'.

```
ceph-deploy new mon1
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.31.png)  

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.32.png)  

用vim编辑ceph.conf文件。

```
vim ceph.conf
```

在[全局]块下，粘贴下面的配置。

```
# Your network address
public network = 10.0.15.0/24
osd pool default size = 2
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.33.png)  

现在，在mon1节点上部署Ceph-mon。

```
ceph-deploy mon create-initial
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.34.png)  

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.35.png)  

检查/dev/sdb分区在所有OSD节点上是否可用。

```
ceph-deploy disk list osd1 osd2 
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.36.png)  

接下来，使用zap选项删除所有节点上的/dev/sdb分区表。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.37.png)  

现在准备好所有OSDS节点。确保结果中没有错误。

```
ceph-deploy osd prepare osd1:/dev/sdb
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.38.png)  

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.39.png)  

接下来，将管理密钥部署到所有相关节点。

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.40.png)  

通过在所有节点上运行下面的命令来更改密钥文件的权限。

```
sudo chmod 644 /etc/ceph/ceph.client.admin.keyring
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.41.png)  

进入ceph

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.42.png)  

检查群集状态。

```
sudo ceph -s
```

![image](https://github.com/anmyles/cloudcomp/blob/master/image/4.43.png)  