# 是否已通过配置文件设置警告天数等于7天

- 操作方法
```
1.修改新建用户的配置文件
sed -i '/^PASS_WARN_AGE.*/s/.*/PASS_WARN_AGE 7/' /etc/login.defs
2.修改已有用户（参考备注）
chage -W 7 YourUserName
```

- 判断依据
> 1. 根据/etc/login.defs文件的PASS_WARN_AGE是否为7判断
> 2. 根据所有可登录bash的用户的warning是否等于90判断
```
查找所有需检查的用户
awk -F: '$3>500||$3==0{if($7!="/sbin/nologin")print $1}' /etc/passwd
```
```
确定所有用户的密码失效时间
chage -l 上一条命令查找的用户|awk -F: '/warning/{print $2}' 是否等于7
```


- 备注
> 无