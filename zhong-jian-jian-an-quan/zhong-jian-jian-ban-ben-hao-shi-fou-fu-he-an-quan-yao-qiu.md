# 中间件版本号是否符合安全要求

* 操作方法
> 以下为各软件的版本要求（各软件版本须不低于如下），安装方法参考官网
  - nginx----> [nginx-1.16.1](http://nginx.org/en/download.html)
  - haproxy---->[haproxy-2.0](https://www.haproxy.org/download/2.0/src/)
  - apache---->[apache-2.4.41](https://httpd.apache.org/download.cgi)
  - tomcat---->[tomcat-8.5.45](https://tomcat.apache.org/download-80.cgi)
  - weblogic---->[weblogic-12.2.1.3](https://www.oracle.com/technetwork/cn/middleware/weblogic/downloads/wls-main-091116-zhs.html)
  - websphere---->[websphere-8.5.5](https://www.ibm.com/developerworks/cn/downloads/ws/was/index.html)

* 判断依据

  > 根据相应的中间件版本号是否符合操作方法要求的版本号判断
  ```
  nginx -v
  haproxy -v
  httpd -v
  /apache-tomcat-8.5.45/bin/version.sh
  ```

* 备注

  > 无



