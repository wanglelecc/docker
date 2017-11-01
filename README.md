# docker
Docker Dockerfile


## 构建镜像
```shell
docker build -t wanglelecc/development-web-server .
```

## 镜像相关命令
```shell
# 列表
docker images

# 删除镜像
docker rmi <your username>/centos-node-hello
```

## 运行镜像
```shell
docker run -p 220:22 -p 800:80 -p 33060:3306 -p 63790:6379 -p 11211:11211 -d  --name="web-server" wanglelecc/development-web-server
```

## 容器相关命令
```shell
# 运行中容器列表
docker ps

# 全部容器列表
docker ps -a

# 删除容器
docker rm <your name>

# 停止容器
docker stop <your name>

# 启动容器
docker start <your name>
```