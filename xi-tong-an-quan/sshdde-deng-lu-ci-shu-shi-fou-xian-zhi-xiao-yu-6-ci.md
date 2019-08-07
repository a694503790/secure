# sshd的登录次数是否限制小于6次

- 操作方法
```
sed -i '/MaxAuthTries/s/.*/MaxAuthTries 6/' /etc/ssh/sshd_config 
```

- 判断依据
> 根据/etc/ssh/sshd_config文件的MaxAuthTries小于6判断


- 备注
> 无