# 是否具备完备的数据库备份机制（满足异机存放）

- 操作方法
> 1.主节点按照[是否开启二进制日志](./shi-fou-kai-qi-ri-zhi-shen-ji-gong-neng-ff08-cha-xun-ri-zhi-3001-cuo-wu-ri-zhi-3001-er-jin-zhi-ri-zhi-ff09.md)操作开启二进制
> 2.从节点按照[是否采用主从同步或集群的高可用模式](./shi-fou-cai-yong-ji-qun-huo-ff08-zhu-cong-ff09-tong-bu-fu-zhi-de-gao-ke-yong-mo-shi.md)操作开启主从同步
> 3.备份节点
> - 全量备份
> 1. dfdsf
> - 增量备份
- 判断依据
> 通过备份节点是否有完备的数据库备份，是否已加入计划任务进行判断

- 备注
> 异机存放的节点不能是主/从节点，如机器不够的可备注声明，同时在从库进行binlog的进行备份

