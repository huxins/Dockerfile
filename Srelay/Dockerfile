# https://socks-relay.sourceforge.io/samples.html

FROM debian:stretch-slim

WORKDIR /home/

RUN set -x \
  && sed -i s@/deb.debian.org/@/mirrors.tuna.tsinghua.edu.cn/@g  /etc/apt/sources.list \
  && sed -i s@/security.debian.org/@/mirrors.aliyun.com/@g  /etc/apt/sources.list \
  && apt-get update && apt-get install -y \
  wget build-essential \
  && wget https://nchc.dl.sourceforge.net/project/socks-relay/socks-relay/srelay-0.4.8/srelay-0.4.8p3.tar.gz \
  && tar zxvf srelay-0.4.8p3.tar.gz \
  && cd srelay-0.4.8p3 \
  && ./configure \
  && make

FROM debian:stretch-slim

WORKDIR /root/

COPY --from=0 /home/srelay-0.4.8p3/srelay .

RUN echo "0.0.0.0 any" > srelay.conf

ENTRYPOINT [ "./srelay", "-q", "-f", "-c ./srelay.conf" ]

CMD ["-i:1080"]