# 是否已禁止中间件目录列出

* 操作方法
  ```
  shell> vim /etc/httpd/conf/httpd.conf  
  Options Indexes FollowSymLinks
  ```
  > 将上方的Indexes去掉（大约在331行）改成下方后重启apache服务
  ```
  Options FollowSymLinks
  ```
* 判断依据

  > 在/var/www/html目录下创建目录testdo1,在本机使用
  >
  > ```
  > curl http://127.0.0.1/testdo1/ #是否返回403判断
  > ```

* 备注

  > Tomcat8.5以上默认关闭，如是nginx、haproxy、apache、weblogic、websphere则填是即可



