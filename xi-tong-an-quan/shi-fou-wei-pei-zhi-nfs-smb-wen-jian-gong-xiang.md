# 是否未配置nfs/smb文件共享

- 操作方法
> Linux默认关闭该功能，如已开启，请关闭，关闭方法：
```
关闭smb
[CentOS Linux 7]
systemctl stop smb.service && systemctl disable postfix.smb
[CentOS Linux 6]
service smb stop && chkconfig smb off
关闭nfs
sdfsd
```
- 判断依据
> 通过netstat -lntp 判断是否存在smb或nfs进程

- 备注
> 如否请在备注列出访问ip及用户并确认配置文件已正确配置