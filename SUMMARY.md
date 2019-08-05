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
* 中间件安全
* 应用安全

