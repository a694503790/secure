# /etc/passwd下无需登录的服务账号是否均为/sbin/nologin，有特殊的请备注

- 操作方法
```
sed -i '/LogLevel/s/.*/LogLevel INFO/' /etc/ssh/sshd_config 
```

- 判断依据
> 根据/etc/ssh/sshd_config文件的LogLevel为INFO以上判断

- 备注
> 无