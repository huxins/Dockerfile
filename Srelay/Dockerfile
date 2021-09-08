FROM debian:stretch-slim
WORKDIR /build
RUN set -x \
  && apt-get update \
  && apt-get install -y \
    wget build-essential \
  && wget https://downloads.sourceforge.net/project/socks-relay/socks-relay/srelay-0.4.8/srelay-0.4.8p3.tar.gz \
  && tar -zxf srelay-0.4.8p3.tar.gz \
  && cd srelay-0.4.8p3 \
  && ./configure \
  && make

FROM debian:stretch-slim
WORKDIR /app
COPY --from=0 /build/srelay-0.4.8p3/srelay .
RUN echo "0.0.0.0 any" > srelay.conf
ENTRYPOINT [ "./srelay", "-q", "-f", "-c ./srelay.conf" ]
CMD ["-i :1080"]
