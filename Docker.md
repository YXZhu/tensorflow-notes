# Docker Run  tensorflow 使用Docker运行tensorflow 同时挂载目录
```
docker run --runtime=nvidia --rm -it -v /home/zhuyix/:/root/tensorflow --name zhuyix tensorflow/tensorflow:latest-gpu
```
