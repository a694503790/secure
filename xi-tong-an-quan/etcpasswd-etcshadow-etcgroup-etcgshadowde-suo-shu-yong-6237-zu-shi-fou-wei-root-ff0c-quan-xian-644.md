# /etc/passwd /etc/shadow /etc/group /etc/gshadow的所属用户/组是否为root，权限644

- 操作方法
```
chown root:root /etc/passwd /etc/shadow /etc/group /etc/gshadow && chmod 0644 /etc/group && chmod 0644 /etc/passwd && chmod 0400 /etc/shadow && chmod 0400 /etc/gshadow
```

- 判断依据
> 根据/etc/passwd /etc/shadow /etc/group /etc/gshadow的所属用户/组是否为root，权限是否为644判断

- 备注
> 无