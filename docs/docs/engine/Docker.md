# Docker

## 安装引擎

系统环境：`CentOS7`

1. 查看已安装的Docker

```shell
yum list installed | grep docker
```

2. 卸载已安装的Docker

```shell
sudo yum remove -y 名称
```

3. 删除已创建的容器镜像

```shell
sudo rm -rf /var/lib/docker
```

4. 安装依赖包

```shell
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

5. 使用阿里云的镜像

```shell
sudo yum-config-manager --add-repo https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo 
```

6. 安装Docker

```shell
sudo yum install docker-ce
```

7. 启动Docker

```shell
sudo systemctl start docker
```

8. 设置开机自启

```shell
sudo systemctl enable docker
```

9. 查看版本

```shell
docker --version
```

10. 修改镜像服务器地址,地址为自己的阿里云镜像服务器地址

```shell
vim /etc/docker/daemon.json
{
	"registry-mirrors": ["https://yk2n9tnm.mirror.aliyuncs.com"]
}
```

## 安装GUI

GUI工具：``Portainer``

1. 首先创建容器并运行 映射端口

```shell
docker volume create portainer_data

docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

2. 然后访问 IP:9000 进入Portainer界面，设置默认账号。

## 常用命令

## 开放外部访问

1. 修改docker配置文件

```shell
vi /usr/lib/systemd/system/docker.service

#修改ExecStart 最后面增加-H tcp://0.0.0.0:2375
ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock -H tcp://0.0.0.0:2375
```

2. 然后重启服务

```shell
sudo systemctl restart docker
```



