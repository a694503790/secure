# openssh版本是否不低于openssh-8.0p1

- 操作方法
> Linux默认关闭该功能，如已开启，请关闭，关闭方法：
```
yum remove telnet-server 
```

- 判断依据
> ssh -V 的命令结果大于OpenSSH_8.0p1

- 备注
> 无