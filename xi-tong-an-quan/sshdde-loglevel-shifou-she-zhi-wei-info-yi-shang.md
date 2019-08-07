# sshd的LogLevel是否设置为INFO以上

- 操作方法
> Linux默认关闭该功能，如已开启，请关闭，关闭方法：
```
sed -i '/LogLevel/s/#//' /etc/ssh/sshd_config 
```

- 判断依据
> 根据/etc/ssh/sshd_config文件的LogLevel是否取消注释判断

- 备注
> 无