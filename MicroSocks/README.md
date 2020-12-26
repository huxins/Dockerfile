# MicroSocks

```shell
$ docker build -t microsocks:latest https://github.com/huxins/Dockerfile.git#:MicroSocks
$ docker run -d --restart always -p 1080:1080 -e USERNAME=USERNAME -e PASSWORD=PASSWORD --name microsocks huxins/microsocks:latest
```


