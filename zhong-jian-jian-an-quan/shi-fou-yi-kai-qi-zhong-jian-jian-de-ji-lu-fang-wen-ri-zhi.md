# 是否已开启中间件的记录访问日志

- 操作方法
```
# Tomcat8.5以上默认关闭，如未关闭请参考下方
shell> vim /apache-tomcat-8.5.45/conf/tomcat-users.xml  
<!--
  <role rolename="tomcat"/>
  <role rolename="role1"/>
  <user username="tomcat" password="<must-be-changed>" roles="tomcat"/>
  <user username="both" password="<must-be-changed>" roles="tomcat,role1"/>
  <user username="role1" password="<must-be-changed>" roles="role1"/>
-->
  # 按照如上要求注释上方内容即可
```
- 判断依据
> 根据tomcat-users.xml是否已注释rolename和username判断
```
grep "<role " tomcat-users.xml -C1|grep '<!--' #是否为假
```

- 备注
> Tomcat8.5以上默认关闭，如是Weblogic/Websphere则填是并备注说明

