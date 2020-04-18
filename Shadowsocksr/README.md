# shadowsocks-libev Dockerfile

- [shadowsocksrr/shadowsocksr](https://github.com/shadowsocksrr/shadowsocksr)
- [shadowsocksr-backup/shadowsocksr](https://github.com/shadowsocksr-backup/shadowsocksr)

```shell
$ docker build -t ssr:v1 https://github.com/huxins/Dockerfile.git#:Shadowsocksr
$ docker run --name ssr --restart=always -p 1081:1081 -p 1081:1081/udp -d ssr:v1
```











