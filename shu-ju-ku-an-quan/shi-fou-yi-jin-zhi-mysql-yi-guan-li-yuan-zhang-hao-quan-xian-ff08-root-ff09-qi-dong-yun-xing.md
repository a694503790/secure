# 是否已禁止mysql以管理员帐号权限（root）启动运行

- 操作方法
```
shell> vim /etc/my.cnf  
# 添加如下项
[mysqld]
user=mysql
```


- 判断依据
> 根据 grep "user=mysql" /etc/my.cnf|grep -v '#'是否为真判断

- 备注
> 无

