# 是否已开启中间件的记录访问日志

* 操作方法
  >

* 判断依据

  > 根据tomcat-users.xml是否已注释rolename和username判断
  >
  > ```
  > grep "<role " tomcat-users.xml -C1|grep '<!--' #是否为假
  > ```

* 备注

  > Tomcat8.5以上默认开启，如是Weblogic/Websphere则填是并备注说明



