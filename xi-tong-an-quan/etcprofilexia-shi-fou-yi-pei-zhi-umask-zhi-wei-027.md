# /etc/profile下是否已配置umask值为027

- 操作方法
```
echo "umask 027" >>/etc/profile && source /etc/profile
```

- 判断依据
> 根据新创建的文件权限是否为640判断

- 备注
> 无