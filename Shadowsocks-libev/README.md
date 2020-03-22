# shadowsocks-libev Dockerfile

- [shadowsocks-libev Dockerfile](https://github.com/shadowsocks/shadowsocks-libev/blob/master/docker/alpine/Dockerfile)
- [不编译shadowsocks的文档](https://lixingcong.github.io/2016/07/20/compile-with-no-doc-for-shadowsocks/)

```shell
$ docker build -t ss:v1 https://github.com/huxins/Dockerfile.git#:Shadowsocks-libev
$ docker run -e PASSWORD=<password> -p 8388:8388 -p 8388:8388/udp -d shadowsocks/shadowsocks-libev
```











