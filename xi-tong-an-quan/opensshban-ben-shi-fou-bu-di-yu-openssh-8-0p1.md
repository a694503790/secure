# openssh版本是否不低于openssh-8.0p1

- 操作方法
>注：升级ssh存在一定的危险性，一旦不成功可能无法通过远程连接到系统，因此在升级之前须安装vnc或者telnet等远程服务,升级后再关闭
查看下当前SSH版本：
```
ssh -V
rpm -qa | grep openssh
```
> 1.[下载openssh](https://openbsd.hk/pub/OpenBSD/OpenSSH/portable/)
> 
> 2.安装依赖包
```
yum install gcc openssl-devel zlib-devel
```
> 3.解压安装包
```
tar -zxvf openssh-7.7p1.tar.gz
```
> 4.编译
```
./configure
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
> 7.修改SSHD服务文件
```
vim /etc/init.d/sshd
修改以下内容
SSHD=/usr/sbin/sshd 为 SSHD=/usr/local/sbin/sshd
/usr/sbin/ssh-keygen -A 为 /usr/local/bin/ssh-keygen -A 
保存退出
```
> 8.复制sshd配置文件
```
cp sshd_config /etc/ssh/sshd_config
```
> 9.修改初始化配置文件
```
vim /etc/init.d/sshd
在 ‘$SSHD $OPTIONS && success || failure’这一行上面加上一行 ‘OPTIONS="-f /etc/ssh/sshd_config"’
保存退出
```
> 10.重启ssh服务：
```
service sshd restart
```
> 11.查看下安装结果：
```
ssh -V
```
> 至此升级/安装完成。
- 判断依据
> ssh -V 的命令结果大于OpenSSH_8.0p1

- 备注
> 无