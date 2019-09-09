### 系统安全

- root用户的authorized_keys是否无信任的公钥

- sshd是否禁止空密码登录

- sshd是否强制V2 Protocol

- sshd的LogLevel是否设置为INFO以上

- sshd是否禁止root远程登录

- sshd空闲超时退出时间是否大于5分钟

- sshd的登录次数是否限制小于6次

- openssh版本是否不低于openssh-8.0p1

- /etc/passwd除root外是否无UID为0的高权限账号

- /etc/passwd下无需登录的服务账号是否均为/sbin/nologin，有特殊的请备注

- 所有账号密码是否为8位以上，且同时具备小写字母、大写字母、数字、特殊字符

- 是否已通过配置文件配置密码复杂度要求

- 是否已通过配置文件配置密码失效时间等于90天

- 是否已通过配置文件配置密码修改最小间隔时间等于7天

- 所有账号密码是否已通过配置文件设置警告天数等于7天

- /etc/passwd /etc/shadow /etc/group /etc/gshadow的所属用户/组是否为root，权限644

- 是否已通过配置文件设定记录所有用户的登录和操作日志

- 是否已通过配置文件打开rsyslog日志记录

- /etc/profile下是否已配置umask值为027

- 服务端口监听是否最小化

- 是否未配置nfs/smb文件共享，如否请在备注列出访问ip及用户并确认配置文件已正确配置
