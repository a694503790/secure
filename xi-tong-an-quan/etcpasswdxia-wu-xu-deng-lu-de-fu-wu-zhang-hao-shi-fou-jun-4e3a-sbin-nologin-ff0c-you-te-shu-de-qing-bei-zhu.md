# /etc/passwd下无需登录的服务账号是否均为/sbin/nologin，有特殊的请备注

- 操作方法
```
awk -F: '$3>500{if($7=="/bin/bash"&&$1!="mysql")print $0}' /etc/passwd
```

- 判断依据
> 根据/etc/ssh/sshd_config文件的LogLevel为INFO以上判断

- 备注
> mysql无需备注