# https://github.com/shadowsocksr-backup/shadowsocksr-libev
# https://github.com/shadowsocksrr/shadowsocksr-libev/tree/Akkariiin/master

FROM debian:stretch-slim

RUN set -x \
  && runDeps="build-essential autoconf libtool libssl-dev libpcre3-dev asciidoc xmlto zlib1g-dev git" \
  && sed -i s@/deb.debian.org/@/mirrors.tuna.tsinghua.edu.cn/@g  /etc/apt/sources.list \
  && sed -i s@/security.debian.org/@/mirrors.aliyun.com/@g  /etc/apt/sources.list \
  && apt-get update && apt-get install -y --no-install-recommends \
      ${runDeps} gettext ca-certificates \
  && rm -rf /var/lib/apt/lists/* \
  && git clone --depth=1 https://github.com/shadowsocksr-backup/shadowsocksr-libev.git /tmp/repo/shadowsocksr-libev \
  && cd /tmp/repo/shadowsocksr-libev \
  && ./configure --prefix=/usr --disable-documentation \
  && make && make install \
  && apt-get autoclean \
  && apt-get purge -y --auto-remove ${runDeps} \
  && rm -rf /tmp/repo

ENV TZ Asia/Shanghai
COPY ss-local.json /etc

ENTRYPOINT ["ss-local", "-c", "/etc/ss-local.json"]
