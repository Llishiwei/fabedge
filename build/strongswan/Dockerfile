FROM alpine:3.13.6

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories && \
    apk --update add strongswan && \
    rm -rf /var/cache/apk/*

RUN sed -i 's/# install_routes = yes/install_routes = no/' /etc/strongswan.d/charon.conf

EXPOSE 500/udp 4500/udp

CMD ["/usr/sbin/ipsec", "start", "--nofork"]
