# 是否已删除默认test库

- 操作方法
```
建议：
shell> /mysql/bin/mysql_secure_installation
```
```
可选：
mysql> show databases;
mysql> drop database test; 
```

- 判断依据
> 根据 show databases 是否有test库做判断

- 备注
> mysql5.7以上默认无test库，5.7以下均需执行

