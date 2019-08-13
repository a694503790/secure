# 是否开启日志审计功能（查询日志、错误日志、二进制日志）

- 操作方法
```
shell > vim /etc/my.cnf  
# 增加如下项
[mysqld]
 bind-address = 127.0.0.1 or bind-address = 192.168.1.5 
```



- 判断依据
> 根据防火墙的规则是否符合《sheet 服务器清单汇总表》填写的端口判断

- 备注
> 无

