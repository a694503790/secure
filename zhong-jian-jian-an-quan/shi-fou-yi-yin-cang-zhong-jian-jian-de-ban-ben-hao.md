# 是否已隐藏中间件的版本号

* 操作方法
> 1. 以下为**apache**的隐藏方法（默认未隐藏），其它中间件请看备注
  ```
  shell> vim /etc/httpd/conf/httpd.conf  
  ServerSignature On 
  ServerTokens OS
  ```
  > 将上方的ServerSignature和ServerTokens改成下方后重启apache服务
  ```
  ServerSignature Off
  ServerTokens Prod
  ```
  > *如果没有ServerSignature和ServerTokens手工添加即可*
  > 
  2. 以下为**tomcat**的隐藏方法（默认未隐藏），其它中间件请看备注
  ```
  shell> unzip /apache-tomcat-9.0.24/lib/catalina.jar
  shell> vim ServerInfo.properties
  ```
  ```
  server.info=Apache Tomcat/9.0.24
  server.number=9.0.24.0
  server.built=Aug 14 2019 21:16:42 UTC
  ```
  &nbsp; &nbsp; 修改成
  ```
  server.info=Apache Tomcat
  server.number=0.0.0.0
  server.built=Aug 14 2019 21:16:42 UTC
  ```
  ```
  shell> mv /apache-tomcat-9.0.24/lib/catalina.jar{,.bak}
  shell> jar -cvf catalina.jar org/ META-INF/
  ```
  &nbsp; &nbsp; 最后重启Tomcat
  3. 以下为**nginx**的隐藏方法（默认未隐藏），其它中间件请看备注
  ```
  shell> vim /usr/local/nginx/conf/nginx.conf
  # 在http{}中新增如下字段:
  http {
     server_tokens off;
  }
  ```
  > 最后重启nginx服务
  ```
  /usr/local/nginx/sbin/nginx -s reload
  ```
* 判断依据

  > ```
  > curl -I http://127.0.0.1/abcd/ #是否返回版本号判断
  > curl -I http://127.0.0.1:8080/abcd/ #是否返回版本号判断
  > curl -I http://127.0.0.1:8080/abcd/ |grep --color -i tomcat.* #是否返回版本号判断
  > ```

* 备注

  > 如果是haproxy、weblogic、websphere 则无需隐藏



