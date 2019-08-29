# 是否已设置中间件的httpd.conf、Server Root的所属用户所属组及权限（644）

* 操作方法

  > 例如有一个tomcat应用，那么可以通过在两台服务器上各部署一个一模一样的tomcat应用，再通过以下方式达到高可用  
  > 1. 在两个tomcat服务器的前端接入硬件负载均衡（F5、RADWARE）  
  > 2. 在两个tomcat服务器的前端接入云负载均衡（阿里云SLB、腾讯云CLB）  
  > 3. 在两个tomcat服务器部署[keepalive+haproxy](https://www.jianshu.com/p/95cc6e875456)实现冗灾功能
  
* 判断依据

  > 根据实际情况是否符合高可用判断

* 备注

  > 如接入软件负载均衡（nginx）则未实现真正的高可用/冗灾，譬如nginx一旦挂了，那么后端即便有两台应用服务器也是于事无补的，设置高可用模式时须注意设置session共享



