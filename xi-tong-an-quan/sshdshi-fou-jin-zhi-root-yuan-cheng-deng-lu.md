# sshd是否禁止root远程登录

- 操作方法
> Linux默认关闭该功能，如已开启，请关闭，关闭方法：
```
sed -i '/PermitRootLogin/s/.*/PermitRootLogin no/' /etc/ssh/sshd_config 
```

- 判断依据
> 根据/etc/ssh/sshd_config文件的PermitRootLogin是否为no判断

- 备注
> 无