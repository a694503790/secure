# Summary

* [运维安全管理规范](README.md)
* [操作安全](chapter1.md)
* [网络安全](wang-luo-an-quan-yao-qiu.md)
  * [是否已开启防火墙或安全组策略并设置正确的规则进行访问控制](wang-luo-an-quan-yao-qiu/shi-fou-yi-kai-qi-fang-huo-qiang-huo-an-quan-zu-ce-lve-bing-she-zhi-zheng-que-de-gui-ze-jin-xing-fang-wen-kong-zhi.md)
  * [是否已禁止所有服务器的icmp功能](wang-luo-an-quan-yao-qiu/shi-fou-yi-jin-zhi-suo-you-fu-wu-qi-de-icmp-gong-neng.md)
  * [是否已禁止所有服务器的telnet-server功能](wang-luo-an-quan-yao-qiu/shi-fou-yi-jin-zhi-suo-you-fu-wu-qi-de-telnet-server-gong-neng.md)
  * [不同的服务器群是否有采用安全分级的访问策略](wang-luo-an-quan-yao-qiu/bu-tong-de-fu-wu-qi-qun-shi-fou-you-cai-yong-an-quan-fen-ji-de-fang-wen-ce-lve.md)
  * [对直接供远程登陆的服务器是否有特定的安全防护（如vpn、安全组限定源ip、纯内网访问）](wang-luo-an-quan-yao-qiu/dui-zhi-jie-gong-yuan-cheng-deng-lu-de-fu-wu-qi-shi-fou-you-te-ding-de-an-quan-fang-hu-ff08-ru-vpn-3001-an-quan-zu-xian-ding-yuan-ip-3001-chun-nei-wang-fang-wen-ff09.md)
* [系统安全](xi-tong-an-quan.md)
  * root用户的authorized\_keys是否无信任的公钥
  * sshd是否禁止空密码登录
  * sshd是否强制V2 Protocol
  * sshd的LogLevel是否设置为INFO以上
  * sshd是否禁止root远程登录
  * sshd空闲超时退出时间是否大于5分钟
  * sshd的登录次数是否限制小于6次
  * openssh版本是否不低于openssh-8.0p1
  * /etc/hosts.allow及/etc/hosts.deny的所属用户/组是否为root,权限644
  * /etc/hosts.deny是否添加拒绝所有telnet服务
  * /etc/hosts.allow是否添加具体可以ssh服务器的ip/ip段
  * /etc/passwd除root外是否无UID为0的高权限账号
  * /etc/passwd下无需登录的服务账号是否均为/sbin/nologin，有特殊的请备注
  * 所有账号密码是否为8位以上，且同时具备小写字母、大写字母、数字、特殊字符
  * 所有账号密码是否已通过配置文件配置密码复杂度要求
  * 所有账号密码是否已通过配置文件配置密码失效时间
  * 所有账号密码是否已通过配置文件配置密码修改最小间隔时间
  * 所有账号密码是否已通过配置文件配置密码重用限制
  * 所有账号密码是否已通过配置文件设置警告天数为7天
  * /etc/passwd /etc/shadow /etc/group /etc/gshadow的所属用户/组是否为root，权限644
  * 是否已通过配置文件设定记录所有用户的登录和操作日志
  * 是否已通过配置文件打开messages、cron、secure 日志记录
  * /etc/profile下是否已配置umask值为027
  * 服务端口监听是否最小化
  * [是否未配置nfs/smb文件共享](xi-tong-an-quan/shi-fou-wei-pei-zhi-nfs-smb-wen-jian-gong-xiang.md)
* [数据库安全](shu-ju-ku-an-quan.md)
  * 是否已禁止mysql以管理员帐号权限（root）启动运行
  * 是否满足数据库模块/账户最小化权限分配的原则
  * 是否所有数据库账号密码为8位以上，且同时具备小写字母、大写字母、数字、特殊字符
  * 是否已设置所有数据库账号仅本机访问或可信 IP 访问控制（即host不等于%）
  * 是否已禁用所有用户的.mysql\_history（软链到/dev/null）
  * 是否开启日志审计功能（查询日志、错误日志、二进制日志）
  * 是否采用集群或（主从）同步复制的高可用模式
  * 是否具备完备的数据库备份机制（满足异机存放）
  * 是否对用户的敏感数据是否都采用加密的方式来存储
* [中间件安全](zhong-jian-jian-an-quan.md)
  * 是否已创建专用用户启动相应的中间件
  * 是否已关闭中间件的管理控制台
  * 是否已开启中间件的记录访问日志
  * 是否已配置为高可用模式
  * 是否已设置中间件的httpd.conf、Server Root的所属用户所属组及权限（644）
  * [是否已禁止中间件访问 Web 目录之外的任何文件](zhong-jian-jian-an-quan/shi-fou-yi-jin-zhi-zhong-jian-jian-fang-wen-web-mu-lu-zhi-wai-de-ren-he-wen-jian.md)
  * 是否已禁止中间件目录列出
  * 是否已设置错误页面重定向
  * 是否已隐藏中间件的版本号
  * 是否已关闭中间件的TRACE功能
  * 是否已设置中间件禁止运行 CGI 程序
  * 是否已设置中间件绑定监听地址为非0.0.0.0
* [应用安全](ying-yong-an-quan.md)
  * 应用版本更新前是否做好异机存放当前版本的备份再覆盖当前版本
  * 应用系统是否存在单点故障的可能性
  * 应用系统上线前是否经过源代码漏洞扫描
  * 应用系统上线前是否经过Web应用漏洞扫描
  * 应用系统是否有接入第三方提供的抗攻击（DDOS、WAF）服务
  * 应用系统涉及的组件是否监听最小化
  * 应用系统涉及的组件是否使用专用账号启动
  * 应用系统涉及配置数据库的连接池配置账号信息是否已加密
  * 应用系统超级管理员账号是否8位以上，且同时具备小写字母、大写字母、数字、特殊字符

