# 是否已关闭中间件的管理控制台

* 操作方法
> 以下为tomcat的操作方法，其它中间件请看备注
  ```
  shell> vim /apache-tomcat-8.5.45/conf/tomcat-users.xml  
  <!--
  <role rolename="tomcat"/>
  <role rolename="role1"/>
  <user username="tomcat" password="<must-be-changed>" roles="tomcat"/>
  <user username="both" password="<must-be-changed>" roles="tomcat,role1"/>
  <user username="role1" password="<must-be-changed>" roles="role1"/>
  -->
  # 确认已注释上方内容，如未注释请注释即可
  ```
* 判断依据

  > 根据tomcat-users.xml是否已注释rolename和username判断
  >
  > ```
  > grep "<role " tomcat-users.xml -C1|grep '<!--' #是否为假
  > ```

* 备注

  > Tomcat8.5以上默认关闭，如是nginx、haproxy、apache、weblogic、websphere则填是即可



