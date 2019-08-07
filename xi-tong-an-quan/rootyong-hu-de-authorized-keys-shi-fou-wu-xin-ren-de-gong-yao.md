# root用户的authorized_keys是否无信任的公钥

- 操作方法
```
cat /dev/null >/root/.ssh/authorized_keys
```

- 判断依据
> 根据是否可以从远端服务器通过telnet登录到此服务器判断

- 备注
> Windows请填是