# 是否已通过配置文件打开rsyslog日志记录

- 操作方法
> Linux默认已开启，如已关闭，请开启，开启方法：
```
[CentOS Linux 7]
systemctl restart rsyslog
[CentOS Linux 6]
service rsyslog restart
```

- 判断依据
> 根据service rsyslog status、systemctl status rsyslog判断

- 备注
> 无