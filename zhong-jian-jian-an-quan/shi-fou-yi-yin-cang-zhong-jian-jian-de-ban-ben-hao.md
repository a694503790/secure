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
  shell> vim /apache-tomcat-8.5.45/conf/web.xml
  <param-name>listings</param-name>
  <param-value>true</param-value>
  ```
  > 确认上方的value为false，如是true，请改为false并重启tomcat服务
  ```
  <param-name>listings</param-name>
  <param-value>false</param-value>
  ```
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

  > 在/var/www/html 以及 /apache-tomcat-8.5.45/webapps 目录下mkdir testdo1
  >
  > ```
  > curl http://127.0.0.1/testdo1/ #是否返回403判断
  > curl http://127.0.0.1:8080/testdo1/ #是否返回404判断
  > ```

* 备注

  > 如果是haproxy、weblogic、websphere 则无需隐藏



