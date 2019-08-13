# 是否已删除默认test库及默认空用户

- 操作方法
```
建议：
shell> /mysql/bin/mysql_secure_installation
```
```
可选：
mysql> drop database test; 
mysql> delete from mysql.user where user='';
```

- 判断依据
> 根据 show databases 是否有test库以及select host,user from mysql.user where user='' 是否有空用户判断

- 备注
> mysql5.7以上默认无test库以及空用户，5.7以下均需执行

