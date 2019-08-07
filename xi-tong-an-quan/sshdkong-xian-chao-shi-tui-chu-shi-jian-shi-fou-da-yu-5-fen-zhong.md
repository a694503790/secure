# sshd空闲超时退出时间是否大于5分钟

- 操作方法
```
sed -i '/ClientAliveInterval/s/.*/ClientAliveInterval 300/' /etc/ssh/sshd_config 
```

- 判断依据
> 根据/etc/ssh/sshd_config文件的ClientAliveInterval是否大于300判断


- 备注
> 无