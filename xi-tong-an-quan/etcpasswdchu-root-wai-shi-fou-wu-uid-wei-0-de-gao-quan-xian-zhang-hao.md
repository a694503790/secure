# /etc/passwd除root外是否无UID为0的高权限账号

- 操作方法
```
1.查找是否有uid=0的用户
awk -F: '$3==0&&$1!="root"{print $0}' /etc/passwd 
2.使用usermod修改
usermod -u 1090 YourUserName
```

- 判断依据
> 根据awk -F: '$3==0&&$1!="root"{print $0}' /etc/passwd是否为空判断

- 备注
> 无