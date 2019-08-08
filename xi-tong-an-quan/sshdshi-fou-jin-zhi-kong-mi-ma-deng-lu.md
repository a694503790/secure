# sshd是否禁止空密码登录

- 操作方法
```
sed -i '/PermitEmptyPasswords /s/.*/PermitEmptyPasswords no/' /etc/ssh/sshd_config
```

- 判断依据
> 根据/etc/ssh/sshd_config的PermitEmptyPasswords是否为no判断

- 备注
> 无