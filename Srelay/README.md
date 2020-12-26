# Srelay

```shell
$ docker build -t srelay:latest https://github.com/huxins/Dockerfile.git#:Srelay
$ docker run -d --restart always -p 1080:1080 -p 1080:1080/udp  --name srelay huxins/srelay:latest
```


