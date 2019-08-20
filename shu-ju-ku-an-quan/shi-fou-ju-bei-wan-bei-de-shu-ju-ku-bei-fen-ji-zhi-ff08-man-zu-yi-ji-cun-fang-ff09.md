# 是否具备完备的数据库备份机制（满足异机存放）

- 操作方法
> ##### 1.主节点（192.168.1.123）按照[链接](./shi-fou-kai-qi-ri-zhi-shen-ji-gong-neng-ff08-cha-xun-ri-zhi-3001-cuo-wu-ri-zhi-3001-er-jin-zhi-ri-zhi-ff09.md)操作开启二进制日志并创建备份用户
>
```
> # 创建备份用户
mysql> create user root@192.168.1.125 identified by 'Do1admin@123';
mysql> grant all privileges on *.* to root@192.168.1.125;
mysql> flush privileges;
```
> ##### 2.备份节点（192.168.1.125）按照下方操作全量备份
>
```
# 配置免密码
shell> mysql_config_editor set --host=192.168.1.123 --user=root --login-path=125 --password
```
```
# 输入密码后测试登录
shell> mysql --login-path=125
```
```
# 创建全量备份脚本
shell> vim /home/mysql/backup/backup.sh
#!/bin/bash
BakDir=/home/mysql/backup
LogFile=/home/mysql/backup/bak.log
Date=`date +%Y%m%d`
Begin=`date +"%Y年%m月%d日 %H:%M:%S"`
mkdir -p /home/mysql/backup
cd $BakDir
DumpFile=$Date.sql
GZDumpFile=$Date.sql.tgz
mysqldump --login-path=125 --events --all-databases --flush-logs --single-transaction --flush-privileges > $DumpFile
tar -zvcf $GZDumpFile $DumpFile
rm -rf $DumpFile
Last=`date +"%Y年%m月%d日 %H:%M:%S"`
echo 开始:$Begin 结束:$Last $GZDumpFile succ >> $LogFile
```
```
# 按需添加计划任务
crontab -e
0 2 * * * sh /home/mysql/backup/backup.sh
```
- 判断依据
> 通过备份节点是否有完备的数据库备份，是否已加入计划任务进行判断

- 备注
> 异机存放的节点可以是从节点

