# 服务端口监听是否最小化

- 操作方法
> 仅列出关闭25端口的方法
```
[CentOS Linux 7]
systemctl stop postfix.service && systemctl disable postfix.service
[CentOS Linux 6]
service postfix stop && chkconfig postfix off
```

- 判断依据
> netstat -lntp的监听列表与清单汇总表一致

- 备注
> 除22端口及清单汇总表列出的外均需关闭，如25端口