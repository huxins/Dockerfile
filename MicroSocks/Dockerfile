FROM debian:buster

RUN set -ex \
 && sed -i 's/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apt/sources.list \
 && sed -i 's/security.debian.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apt/sources.list \
 && apt-get update && apt-get install -y --no-install-recommends \
     git ca-certificates build-essential \
 && rm -rf /var/lib/apt/lists/* \
 && git clone --depth=1 https://github.com/rofl0r/microsocks.git /tmp/repo/microsocks \
 && cd /tmp/repo/microsocks \
 && make install \
 && apt-get autoclean \
 && apt-get purge -y --auto-remove build-essential git \
 && cd ~ \
 && rm -rf /tmp/repo

CMD microsocks -1 -i 0.0.0.0 -p 1080 -u $USER_NAME -P $PASSWORD -b 0.0.0.0