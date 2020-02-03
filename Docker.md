# 什么是Docker
见链接 [Docker 介绍，安装](https://yeasy.gitbooks.io/docker_practice/)

# Docker Run  tensorflow 
Nvidia-docker 出现如下报错
> `docker: Error response from daemon: Unknown runtime specified nvidia.`

修改 /etc/docker/daemon.json
```
{
    "runtimes": {
        "nvidia": {
            "path": "/usr/bin/nvidia-container-runtime",
            "runtimeArgs": []
        }
    }
}
```

## 使用Docker运行tensorflow 同时挂载目录
```
docker run --runtime=nvidia --rm -it -v /home/zhuyix/:/root/tensorflow --name zhuyix tensorflow/tensorflow:latest-gpu
```
docker run的参数含义如下：

1. --rm        退出容器清除数据
2. -it           启动交互式终端
3. -v           挂在目录
4. --name  容器名称

## 退出Docker
> 在容器中退出 ```exit 或 CTRL+D```

> 使用 `docker container stop` 来终止一个运行中的容器。

> 终止状态的容器可以用 `docker container ls -a `命令看到

