#	MySQL

## 安装

系统环境：`CentOS7`

Docker版本：`19.03.11`

使用docker创建mysql并运行,默认密码123456zz

```shell
docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456zz -d mysql
```

通过命令`docker ps -a`或者`poratainer`里查看是否启动成功

使用Navicate连接数据库

![navicate](../../imgs/navicate.png)