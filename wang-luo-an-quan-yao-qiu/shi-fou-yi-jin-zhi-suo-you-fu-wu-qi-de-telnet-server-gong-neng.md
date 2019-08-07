# 是否已禁止所有服务器的telnet-server功能

- 操作方法
> Linux默认是不开启该功能，但升级openssh过程中将会先打开该功能以作为backup，关闭方法：
```
yum remove telnet-server 
```

- 判断依据
> 根据是否可以从远端服务器通过telnet登录到此服务器判断

- 备注
> Windows请填是