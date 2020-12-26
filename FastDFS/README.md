# FastDFS


## 目录介绍
### conf 
Dockerfile 所需要的一些配置文件
当然你也可以对这些文件进行一些修改  比如 storage.conf 里面的 bast_path 等相关

## 使用方法
需要注意的是 你需要在运行容器的时候制定宿主机的ip 用参数 FASTDFS_IPADDR 来指定

```bash
docker build -t fastdfs:latest https://github.com/huxins/Dockerfile.git#:FastDFS

docker run -d --restart always -e FASTDFS_IPADDR=192.168.1.234 -p 8888:8888 -p 22122:22122 -p 23000:23000 --name fastdfs huxins/fastdfs:latest

docker run -d --restart always --net=host -v /root/fastdfs:/home/dfs/data -e FASTDFS_IPADDR=118.24.98.35 --name fastdfs huxins/fastdfs:latest
```

