# Shadowsocksr

```shell
$ docker build -t shadowsocksr:latest https://github.com/huxins/Dockerfile.git#:Shadowsocksr
$ docker run --name ssr --restart=always -p 1081:1081 -p 1081:1081/udp -d shadowsocksr:latest
```


