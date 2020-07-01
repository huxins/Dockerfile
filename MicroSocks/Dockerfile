FROM alpine:3.11

RUN set -ex \
 && sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories \
 && apk add --no-cache --virtual .build-deps \
     git \
     build-base \
 && git clone --depth=1 https://github.com/rofl0r/microsocks.git /tmp/repo/microsocks \
 && cd /tmp/repo/microsocks \
 && make install \
 && apk del .build-deps \
 && cd ~ \
 && rm -rf /tmp/repo

CMD microsocks -b -i 0.0.0.0 -p 1080 -u $USER_NAME -P $PASSWORD