# 实验1

## 实验环境

Ubuntu 20.04 Server 64bit

### 当前 Linux 发行版基本信息

命令为:

 `lsb_release -a `

 虚拟机的发行版情况：

![虚拟机发行版](img/虚拟机发行.png)

云端平台的发行版：

![云端发行版](img/remote-lsb.png)

### 当前 Linux 内核版本信息

命令为：

`uname -r`

虚拟机的内核版本信息：

![虚拟机内核](img/虚拟机内核版本.png)

云端平台的内核版本：

![云端内核](img/remote_uname.png)

## Virtualbox 安装完 Ubuntu 之后新添加的网卡如何实现系统开机自动启用和自动获取 IP？

网卡1设置为`NAT`，新增的网卡3和网卡2保持一致，设置为`Host-only`网络。

查看网卡情况

`sudo apt install net-tools`

![查看网卡](img/查看网卡.png)

再次使用`ifconfig `和`ifconfig -a`

![ifconfig查看](img/ifconfig.png)


![ifconfig-a查看](img/ifconfig-a.png)

表明网卡3即 `enp0s9`,存在但是没有激活。

找到相应的`yaml` 文件：

![查看信息](img/查看信息.png)

再使用 `sudo vim`指令对此文件进行修改，激活网卡3：

![修改配置](img/修改配置.png)

查看修改后的情况，可知网卡3已激活。

![修改后](img/修改后.png)

## 如何使用 scp 在「虚拟机和宿主机之间」、「本机和远程 Linux 系统之间」传输文件

### 虚拟机与宿主机

在宿主机设置一个测试文件 'Test.txt`

首先是宿主机传输文件到虚拟机：

使用指令`scp C:/Users/陈锦兰/Desktop/Test.txt cuc@192.168.56.101:~/`

![宿主机传输](img/宿主机到虚拟机.png)

在虚拟机上查看是否收到, `ls`之后发现此目录下存在`test.txt`文件，用 `cat`命令打开即可。

![虚拟机收到](img/虚拟机收到.png)

然后是虚拟机传输文件到宿主机：

指令为：`scp cuc@192.168.56.101:/home/cuc/Test.txt ./`


然后在宿主机查看是否收到：

![宿主机收到](img/宿主机收到.png)

### 本地与云端 ###

本地传输到云端

指令为 `scp C:/Users/陈锦兰/Desktop/test.txt root@101.133.128.31:root`

![本地传输](img/本地传送.png)

云端传输到本地

指令为  `scp root@101.133.128.31:/root/root ./`



### 如何配置 SSH 免密登录？

使用指令 `ssh-keygen -t rsa`，来生成密钥

![生成密钥](img/生成密钥.png)

在终端中执行scp远程拷贝命令

`scp C:/Users/陈锦兰/.ssh/id_rsa.pub cuc@192.168.56.101:~/.ssh`

![复制ssh文件到虚拟机](img/ssh复制到虚拟机.png)

 再执行指令：`cp  id_rsa.pub  authorized_keys`,将公钥复制为authorized_keys文件

 查看结果

 ![配置成功](img/ssh配置成功.png)

</br>

参考资料

https://www.jianshu.com/p/e9db116fef8c
https://blog.csdn.net/xiongyangg/article/details/110206220