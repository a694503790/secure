# 是否具备完备的数据库备份机制（满足异机存放）

- 操作方法
> 1.主节点（192.168.1.123）按照[链接](./shi-fou-kai-qi-ri-zhi-shen-ji-gong-neng-ff08-cha-xun-ri-zhi-3001-cuo-wu-ri-zhi-3001-er-jin-zhi-ri-zhi-ff09.md)操作开启二进制日志并创建备份用户
>
```
> # 创建备份用户
mysql> create user root@192.168.1.125 identified by '1qaz#EDC2wsx';
mysql> grant all privileges on *.* to root@192.168.1.125;
mysql> flush privileges;
```
> 2.备份节点（192.168.1.125）按照下方操作全量备份
>
```
> # 创建
ddd
```
- 判断依据
> 通过备份节点是否有完备的数据库备份，是否已加入计划任务进行判断

- 备注
> 异机存放的节点可以是从节点

