# Dockerfile

```shell
$ docker build -t nginx:v3 .
```

直接用 Git repo 进行构建

```shell
$ yum install -y https://centos7.iuscommunity.org/ius-release.rpm
$ yum swap git git2u
$ docker build -t ss:v1 https://github.com/huxins/Dockerfile.git#master:Shadowsocks-libev
```

用给定的 tar 压缩包构建

```shell
$ docker build http://server/context.tar.gz
```

从标准输入中读取 Dockerfile 进行构建

```shell
docker build - < Dockerfile
cat Dockerfile | docker build -
```

从标准输入中读取上下文压缩包进行构建（gzip、bzip2 、 xz）

```shell
$ docker build - < context.tar.gz
```


