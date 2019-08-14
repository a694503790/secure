# 是否采用主从同步或集群的高可用模式

- 操作方法
> 1. 主节点[192.168.1.123]
```
# 主节点修改配置文件，增加如下项
shell > vim /etc/my.cnf  
[mysqld]
server-id = 1
log_bin = bin.log
# 主节点执行mysql命令
mysql> CREATE USER 'repl'@'192.168.1.124' IDENTIFIED BY '1qaz#EDC2wsx';
mysql> GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%';
mysql> flush privileges;
mysql> show master status; #记住File和Position
+---------------------+----------+--------------+------------------+-------------------+
| File                | Position | Binlog_Do_DB | Binlog_Ignore_DB | Executed_Gtid_Set |
+---------------------+----------+--------------+------------------+-------------------+
| zhongtai-bin.000005 |      739 |              |                  |                   |
+---------------------+----------+--------------+------------------+-------------------+
```
> 2. 从节点[192.168.1.124]
```
# 从节点修改配置文件，增加如下项
shell > vim /etc/my.cnf  
[mysqld]
server-id = 2
# 从节点执行mysql命令
mysql> change master to
    -> master_host='192.168.1.123', ###填写master节点的ip 
    -> master_user='repl', ###填写master创建的用户名
    -> master_password='1qaz#EDC2wsx',###填写master创建的密码
    -> master_log_file='zhongtai-bin.000005', ###填写master获取的File
    -> master_log_pos=739; ###填写master获取的Position
mysql> start slave;
```
- 判断依据
> 根据从节点show slave status的结果判断

- 备注
> 无

