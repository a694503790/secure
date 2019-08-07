# openssh版本是否不低于openssh-8.0p1

- 操作方法
>注：升级ssh存在一定的危险性，一旦不成功可能无法通过远程连接到系统，因此在升级之前须安装vnc或者telnet等远程服务,升级后再关闭
查看下当前SSH版本：
```
ssh -V
rpm -qa | grep openssh
```
> [下载最新版openssh](https://openbsd.hk/pub/OpenBSD/OpenSSH/portable/)
>编译安装openssh
> 1.    安装依赖包
>
```
yum install gcc openssl-devel zlib-devel
```
> 2.    解压安装包：
```
tar -zxf openssh-7.7p1.tar.gz
```
>
编译
需要gcc编译器的
```
./configure --prefix=/usr --sysconfdir=/etc/ssh
```
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