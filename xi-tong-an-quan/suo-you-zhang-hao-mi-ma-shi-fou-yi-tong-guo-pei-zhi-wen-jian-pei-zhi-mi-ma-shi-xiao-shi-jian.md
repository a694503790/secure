# 是否已通过配置文件配置密码失效时间等于90天

- 操作方法
```
sed -i '/PASS_MAX_DAYS /s/.*/PASS_MAX_DAYS 90/' /etc/login.defs
```

- 判断依据
> 根据/etc/login.defs文件的PASS_MAX_DAYS是否为90判断


- 备注
> 无