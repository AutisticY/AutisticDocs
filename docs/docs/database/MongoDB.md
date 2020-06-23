#	MongoDB

## 安装

系统环境：`CentOS7`

Docker版本：`19.03.11`

使用docker创建并运行

```shell
docker run -d --name=mongodb -p 27017:27017 --restart=always mongo:latest
```

