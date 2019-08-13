# 是否已禁用所有用户的.mysql_history（软链到/dev/null）

- 操作方法
```
rm -rf /home/mysql/.mysql_history && ln -s /dev/null /home/mysql/.mysql_history
rm -rf /root/.mysql_history && ln -s /dev/null /root/.mysql_history
```

- 判断依据
> 根据ll /root/.mysql_history|grep null判断，
> 根据ll /home/mysql/.mysql_history|grep null判断

- 备注
> 无

