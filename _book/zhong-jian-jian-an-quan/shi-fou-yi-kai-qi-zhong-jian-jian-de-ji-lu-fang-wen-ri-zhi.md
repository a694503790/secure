# 是否已开启中间件的记录访问日志

* 操作方法

```
vim /usr/local/nginx/conf/nginx.conf
access_log  logs/host.access.log  main;
```

* 判断依据

&gt;    dfdddd

> 根据nginx.conf是否有写access\_log判断

* 备注

  > Tomcat8.5、apache默认开启，如是haproxy、apache、weblogic、websphere则填是并备注说明



