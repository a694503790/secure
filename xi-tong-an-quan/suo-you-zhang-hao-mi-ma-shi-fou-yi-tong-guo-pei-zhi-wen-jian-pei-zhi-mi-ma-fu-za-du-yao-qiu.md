# 是否已通过配置文件配置密码复杂度要求

- 操作方法
```
[CentOS Linux 7]
sed -i '/minclass /s/.*/minclass=4/' /etc/security/pwquality.conf
sed -i '/minlen /s/.*/minlen=10/' /etc/security/pwquality.conf
```
```
[CentOS Linux 6]
编辑/etc/pam.d/password-auth 和 /etc/pam.d/system-auth配置文件中包含password requisite pam_cracklib.so 这一行。增加配置minlen（密码最小长度）设置为9-32位，minclass（至少包含小写字母、大写字母、数字、特殊字符等4类字符中的4类）设置为4。如
password    requisite     pam_cracklib.so try_first_pass retry=3 minlen=12 minclass=4
```

- 判断依据
> 根据不同操作系统的配置文件**参考操作方法**判断

- 备注
> 无