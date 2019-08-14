# 是否已设置所有数据库账号仅本机访问或可信 IP 访问控制

- 操作方法
> 1. 设置仅监听本机localhost或本机内网ip
```
shell > vim /etc/my.cnf  
# 增加如下项
[mysqld]
 bind-address = 127.0.0.1 #或为本机内网ip
```
> 2. 设置所有用户仅通过本机localhost或指定ip访问
```
mysql > update mysql.user set host='localhost' where user='do1';
```
- 判断依据
> 1. 根据netstat -lnrp|grep mysql是否为0.0.0.0判断
> 2. 根据select user,host from mysql.user where host = '%' 判断
- 备注
> 即不监听0.0.0.0且host不等于%

