# MicroSocks Dockerfile

```shell
$ docker build -t microsocks:v1 https://github.com/huxins/Dockerfile.git#:MicroSocks
$ docker run -d --restart always -p 1080:1080 -e USER_NAME=USER_NAME -e PASSWORD=PASSWORD --name microsocks microsocks:v1
```











