# 是否已配置为高可用模式

- 操作方法
> &nbsp; &nbsp; &nbsp; &nbsp; 例如有一个tomcat应用，那么可以通过在两台服务器上各部署一个一模一样的tomcat应用，再通过以下方式达到高可用
> 1. 在两个tomcat服务器的前端接入硬件负载均衡（F5、RADWARE）
> 2. 在两个tomcat服务器的前端接入云负载均衡（阿里云SLB、腾讯云CLB）
> 3. 在两个tomcat服务器部署[keepalive+haproxy](https://www.jianshu.com/p/95cc6e875456)
- 判断依据
> 根据实际情况是否符合高可用判断

- 备注
> 无

