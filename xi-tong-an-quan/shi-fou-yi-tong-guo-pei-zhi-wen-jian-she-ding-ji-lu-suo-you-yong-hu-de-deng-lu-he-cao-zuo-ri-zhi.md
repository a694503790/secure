# 是否已通过配置文件设定记录所有用户的登录和操作日志

- 操作方法
>  
> 将如下配置**追加**到/etc/profile
>
```
 export HISTTIMEFORMAT='%F %T  '
 history
 USER=`whoami`
 USER_IP=`who -u am i 2>/dev/null| awk '{print $NF}'|sed -e 's/[()]//g'`
 if [ "$USER_IP" = "" ]; then
 USER_IP=`hostname`
 fi
 if [ ! -d /var/log/history ]; then
 mkdir /var/log/history
 chmod 777 /var/log/history
 fi
 if [ ! -d /var/log/history/${LOGNAME} ]; then
 mkdir /var/log/history/${LOGNAME}
 chmod 300 /var/log/history/${LOGNAME}
 fi
 export HISTSIZE=4096
 DT=`date +"%Y%m%d_%H:%M:%S"`
 export HISTFILE="/var/log/history/${LOGNAME}/${USER}@${USER_IP}_$DT"
 chmod 600 /var/log/history/${LOGNAME}/*history* 2>/dev/null
```
> 执行
```
source /etc/profile
```
- 判断依据
> 根据是否在/var/log/history/有各用户的登录日志及执行命令记录

- 备注
> 无