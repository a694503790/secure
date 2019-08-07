# openssh版本是否不低于openssh-8.0p1

- 操作方法
>注：升级ssh存在一定的危险性，一旦不成功可能无法通过远程连接到系统，因此在升级之前最好先安装vnc或者telnet等远程服务
查看下当前SSH版本：
```
ssh -V
rpm -qa | grep openssh
```
> 下载最新版openssh
https://openbsd.hk/pub/OpenBSD/OpenSSH/portable/openssh-7.7p1.tar.gz
备份ssh配置
```
mv /etc/ssh/   /lee/bak/ssh.bak
``` 
编译安装openssh
1、 解压安装包：
```
tar -zxf openssh-7.7p1.tar.gz
```
2、编译
需要gcc编译器的
```
./configure --prefix=/usr --sysconfdir=/etc/ssh
```
如果报错：
configure: error: *** zlib.h missing - please install first or check config.log ***
需要安装zlib-devel
```
yum install -y zlib-devel
```
如果报错：
configure: error: *** OpenSSL headers missing - please install first or check config.log ***
需要安装openssl-devel
```
yum -y install openssl-devel
```
解决完报错后重新执行
```
./configure --prefix=/usr --sysconfdir=/etc/ssh
make
```
需要测试：make完成后先不要make install，先卸载旧版的openssh
rpm -e --nodeps `rpm -qa | grep openssh`
完成后执行make install:
```
make install
```
查看下安装结果：
```
ssh -V
```
至此编译安装完成。
配置sshd服务
复制启动文件到/etc/init.d/下并命名为sshd，加入开机启动
```
cp contrib/redhat/sshd.init /etc/init.d/sshd
chkconfig --add sshd
```
重启ssh服务：
service sshd restart
至此升级/安装完成。
- 判断依据
> ssh -V 的命令结果大于OpenSSH_8.0p1

- 备注
> 无