# 是否开启二进制日志功能

- 操作方法
```
shell > vim /etc/my.cnf  
# 增加如下项
[mysqld]
server-id = 1
log_bin = bin.log
```

- 判断依据
> 根据mysql> show variables like '%log_bin%' 是否为ON判断

- 备注
> 无

