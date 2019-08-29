# 是否已禁止中间件目录列出

* 操作方法
> 1. 以下为apache的关闭方法，其它中间件请看备注
  ```
  shell> vim /etc/httpd/conf/httpd.conf  
  Options Indexes FollowSymLinks
  ```
  > 将上方的Indexes去掉（大约在331行）改成下方后重启apache服务
  ```
  Options FollowSymLinks
  ```
  2. 以下为tomcat的关闭方法（默认关闭），其它中间件请看备注
  ```
  shell> vim /apache-tomcat-8.5.45/conf/web.xml
  <param-name>listings</param-name>
  <param-value>true</param-value>
  ```
  > 确认上方的value为false，如是true，请改为false并重启tomcat服务
  ```
  <param-name>listings</param-name>
  <param-value>false</param-value>
  ```
* 判断依据

  > 在/var/www/html 以及 /apache-tomcat-8.5.45/webapps 目录下mkdir testdo1
  >
  > ```
  > curl http://127.0.0.1/testdo1/ #是否返回403判断
  > curl http://127.0.0.1:8080/testdo1/ #是否返回404判断
  > ```

* 备注

  > apache默认开启，tomcat默认关闭，如nginx、haproxy、weblogic、websphere则填是即可



