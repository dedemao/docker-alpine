# docker-alpine
使用Alpine作为基础镜像安装PHP7.4及PHP8.3环境

# 说明
dump、php74、php83、server、www为文件夹。其中server/mysql/conf.d文件夹用于映射到/etc/mysql/conf.d/目录，该目录是是MySQL中用于存放额外配置文件的目录。它的主要作用是允许用户或管理员在不修改主配置文件(/etc/my.cnf)的情况下，添加自定义配置或覆盖默认配置。dump文件夹将映射到/docker-entrypoint-initdb.d目录，该目录是Docker官方MySQL镜像中用于初始化数据库的特殊目录。它的主要作用是在容器首次启动时，自动执行目录中的 SQL 脚本或 Shell 脚本，以完成数据库的初始化工作。www目录为网站根目录。

# 开始构建
```
docker-compose up -d
```

# 访问php74
```
http://127.0.0.1
```
或
```
http://127.0.0.1:8074
```

# 访问php83
```
http://127.0.0.1:8083
```
