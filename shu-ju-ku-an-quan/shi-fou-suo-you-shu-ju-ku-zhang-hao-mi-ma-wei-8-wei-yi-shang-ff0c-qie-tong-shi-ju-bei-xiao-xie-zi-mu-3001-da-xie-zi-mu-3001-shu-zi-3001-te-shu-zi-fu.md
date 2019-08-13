# 是否所有数据库账号密码为8位以上，且同时具备小写字母、大写字母、数字、特殊字符

- 操作方法
```
[mysql 5.7]
mysql> update mysql.user set authentication_string=PASSWORD('Do1admin@123') where user='do1';
mysql> flush privileges;
[mysql 5.6]
mysql> update mysql.user set Password=PASSWORD('Do1admin@123') where user='do1';
mysql> flush privileges;
```

- 判断依据
> 1.根据各部门提供登录数据库的账号密码判断
> 2.根据mysql.user表中的authentication_string/password是否为null判断
```
[mysql 5.7]
select user,authentication_string from mysql.user where password='';
[mysql 5.6]
select user,password from mysql.user where password='';
```

- 备注
> 无

