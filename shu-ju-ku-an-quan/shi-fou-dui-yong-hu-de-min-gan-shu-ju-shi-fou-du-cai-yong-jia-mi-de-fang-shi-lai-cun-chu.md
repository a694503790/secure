# 是否对用户的敏感数据是否都采用加密的方式来存储

- 操作方法
```
mysql> create table test_tb (username varchar(32),userpwd char(40) not null);
mysql> insert into test_tb (username,userpwd) values ('do1',sha1('1qaz#EDC2wsx'));
mysql> select * from test_tb;
+----------+------------------------------------------+
| username | userpwd                                  |
+----------+------------------------------------------+
| do1      | 68703bd9d49a66664bfb7f4d36913aa439988c2f |
+----------+------------------------------------------+
1 row in set (0.00 sec)
```

- 判断依据
> 根据应用的用户所存储的密码是否已加密判断

- 备注
> 请在备注侧提供应用的密码所在tables,加密函数(建议sha1)参考[链接](https://dev.mysql.com/doc/refman/5.7/en/encryption-functions.html)

