# root用户的authorized_keys是否无信任的公钥

- 操作方法
```
cat /dev/null >/root/.ssh/authorized_keys
```

- 判断依据
> /root/.ssh/authorized_keys是否为空

- 备注
> 如因自动化发布而必需则填是并备注说明