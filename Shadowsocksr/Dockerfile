# https://github.com/shadowsocksrr/shadowsocksr
# https://github.com/shadowsocksr-backup/shadowsocksr

FROM python:3.7-alpine

RUN set -ex \
    && sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories \
    && apk add --no-cache tar libsodium-dev openssl \
    && wget -O /tmp/shadowsocksr-3.2.2.tar.gz https://github.com/shadowsocksrr/shadowsocksr/archive/3.2.2.tar.gz \
    && tar zxf /tmp/shadowsocksr-3.2.2.tar.gz -C /tmp \
    && mv /tmp/shadowsocksr-3.2.2/shadowsocks /usr/local/ \
    && rm -rf /tmp/shadowsocksr-3.2.2 \
    && rm -f /tmp/shadowsocksr-3.2.2.tar.gz

COPY ./ss-local.json /etc/shadowsocks-r/config.json

CMD [ "/usr/local/shadowsocks/local.py", "-c", "/etc/shadowsocks-r/config.json" ]
