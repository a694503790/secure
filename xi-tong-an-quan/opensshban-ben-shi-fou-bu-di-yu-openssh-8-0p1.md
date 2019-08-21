# openssh版本是否不低于openssh-8.0p1

- 操作方法
> **注：升级ssh存在一定的危险性，一旦不成功可能无法通过远程连接到系统，因此在升级之前务必安装vnc或者telnet等远程服务,升级后再关闭**
>
```
ssh -V #查看当前SSH版本
cp -r /etc/ssh/ /root/ssh_bak #备份ssh配置
```
> 1.[下载openssh](https://openbsd.hk/pub/OpenBSD/OpenSSH/portable/)
```
curl -O https://openbsd.hk/pub/OpenBSD/OpenSSH/portable/openssh-8.0p1.tar.gz
```
> 
> 2.安装依赖包
```
yum install gcc openssl-devel zlib-devel pam-devel -y
```
> 3.解压安装包
```
tar -zxvf openssh-8.0p1.tar.gz
```
> 4.编译
```
cd openssh-8.0p1
./configure --prefix=/usr --sysconfdir=/etc/ssh/  --with-pam --with-zlib
```
> 5.安装
```
make && make install
```
> 6.拷贝ssh服务文件
```
cp ./contrib/redhat/sshd.init /etc/init.d/sshd
chmod +x /etc/init.d/sshd
```
>> 
>> #### 如果是CentOS 7.*的系统先操作如下
```
systemctl disable sshd
mv /usr/lib/systemd/system/sshd.service ~
```
>
> 7.重启ssh服务
```
service sshd restart
```
> 8.加入开机自启动
```
chkconfig --add sshd
```
> 9.查看下安装结果
```
ssh -V
```
> 至此升级/安装完成。
- 判断依据
> ssh -V 的命令结果大于OpenSSH_8.0p1

- 备注
> 以上操作已由创新技术中心在CentOS6.5/CentOS7.5实验无误