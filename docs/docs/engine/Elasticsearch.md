# Elasticsearch

## 安装

系统环境：`CentOS7`

Docker版本：`19.03.11`

1. 创建``elasticsearch``容器并运行 映射了9200和9300端口(推荐命令，不推荐portainer图形界面，因为portainer启动有点问题)

* 9200端口用于外部通讯，基于http协议，程序与es的通信使用9200端口。
* 9300端口遵循tcp协议，jar之间就是通过tcp协议通讯，ES集群之间是通过9300进行通讯

```shell
docker run -d -p 9200:9200 -p 9300:9300 --name elasticsearch elasticsearch
```

2. 访问 IP:9200 查看是否启动成功，也可以在[Portainer](/docs/engine/Docker#安装GUI)中查看

## 概念

* **Document（文档）**

  存储的数据（JSON的格式）

* **Index（索引）**

  