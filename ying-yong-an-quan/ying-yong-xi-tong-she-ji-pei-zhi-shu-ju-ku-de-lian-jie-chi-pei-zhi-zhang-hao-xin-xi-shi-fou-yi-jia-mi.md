# 应用系统涉及配置数据库的连接池配置账号信息是否已加密

- 操作方法
> 以企微云私有化的代码为例
```
shell > vim /wxqyh3.0.4_src/apache-tomcat-8.5.31_admin/webapps/wxqyh/WEB-INF/classes/application.properties
jdbc.driverClassName=com.mysql.jdbc.Driver
jdbc.url=jdbc:mysql://127.0.0.1:3306/wxqyh?useUnicode=true&characterEncoding=utf8&&connectionCollation=utf8mb4_general_ci
jdbc.username=root
jdbc.password=do1admin
jdbc.schema=null
```
以上代码须注释并调整为下方，并确认已加密
```
jdbc.readonly_url=jdbc:mysql://localhost:3306/wxqyh?useUnicode=true&characterEncoding=utf8
jdbc.readonly_username={encrypted}15BmtNjw5WbO1m9/mQjmfQ==
jdbc.readonly_password={encrypted}39UwKN+ezbUnJaraqR8OOw==
```

- 判断依据
> 根据对应的连接池配置账号信息是否已加密判断

- 备注
> 请核查安全自查表中的《web应用包》是否有在软件安全（数据库配置）路径处填写**连接池配置位置**

