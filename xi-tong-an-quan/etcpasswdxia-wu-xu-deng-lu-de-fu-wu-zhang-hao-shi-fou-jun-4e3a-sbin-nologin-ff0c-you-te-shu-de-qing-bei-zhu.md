# /etc/passwd下无需登录的服务账号是否均为/sbin/nologin，有特殊的请备注

- 操作方法
```
1.查找是否有不符合安全要求的用户
awk -F: '$3>500{if($7!="/sbin/nologin"&&$1!="mysql")print $0}' /etc/passwd
2.使用usermod修改
usermod -s /sbin/nologin YourUserName
```

- 判断依据
> 根据awk -F: '$3>500{if($7!="/sbin/nologin"&&$1!="mysql")print $0}' /etc/passwd的结果是否为空判断

- 备注
> mysql无需备注