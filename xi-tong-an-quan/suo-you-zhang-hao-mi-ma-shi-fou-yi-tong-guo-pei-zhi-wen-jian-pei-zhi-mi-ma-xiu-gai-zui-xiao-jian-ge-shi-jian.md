# 是否已通过配置文件配置密码修改最小间隔时间

- 操作方法
```
sed '/^PASS_MIN_DAYS.*/s/.*/PASS_MIN_DAYS 7/' /etc/login.def
```

- 判断依据
> 根据/etc/login.defs文件的PASS_MIN_DAYS是否为7判断


- 备注
> 无