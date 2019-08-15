# 是否满足数据库模块/账户最小化权限分配的原则

- 操作方法
> 1. 应用数据需分库（分模块）存储，禁止将数据插入mysql库
```
mysql> create database wxqyh;
```
> 2. 应用数据需建立独立账号，禁止使用root账号作为应用连接账号
```
mysql> create user do1@localhost identified by 'Do1admin@123';
```
> 3. 应用账号需仅对应用的数据库有权限，对其它库无权限（分的越细越好）
```
mysql> grant all privileges on wxqyh.* to do1@localhost;
mysql> revoke all privileges on mysql.* from do1@localhost;
```
- 判断依据
> 1. 根据show databases是否创建应用数据库判断
> 2. 根据select host,user from mysql.user是否创建应用账号判断
> 3. 根据show grants for [username]@[host]是否创建对应的应用数据库判断

- 备注
> 以上三项均需满足方为满足本项

