# 是否采用主从同步或集群的高可用模式

- 操作方法
> 主节点
```
shell > vim /etc/my.cnf  
# 增加如下项
[mysqld]
server-id = 1
log_bin = bin.log
# 从节点
mysql> CREATE USER 'repl'@'%' IDENTIFIED BY '1qaz#EDC2wsx';
mysql> GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%';
mysql> flush privileges;
```
> Linux的防火墙教程请参考[链接](https://www.linuxprobe.com/chapter-08.html)


- 判断依据
> 根据防火墙的规则是否符合《sheet 服务器清单汇总表》填写的端口判断

- 备注
> 无

