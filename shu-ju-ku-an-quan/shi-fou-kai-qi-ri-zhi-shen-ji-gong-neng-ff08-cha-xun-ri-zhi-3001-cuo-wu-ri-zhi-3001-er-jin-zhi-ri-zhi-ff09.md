# 是否开启日志审计功能（错误日志、二进制日志）

- 操作方法
```
shell > vim /etc/my.cnf  
# 增加如下项
[mysqld]
log_error=error.log
log=select.log
log-bin=bin.log
```



- 判断依据
> 根据防火墙的规则是否符合《sheet 服务器清单汇总表》填写的端口判断

- 备注
> 无

