FROM centos:7
MAINTAINER anexplore
ENV REFRESHED_AT 2018-03-08

RUN yum -y install epel-release && cd /etc/yum.repos.d/ && \
    curl -O https://copr.fedorainfracloud.org/coprs/librehat/shadowsocks/repo/epel-7/librehat-shadowsocks-epel-7.repo && \
    yum install -y libsodium && \
    curl -O http://dl.fedoraproject.org/pub/epel/testing/7/x86_64/Packages/m/mbedtls-2.7.5-1.el7.x86_64.rpm && \
    yum -y install mbedtls-2.7.5-1.el7.x86_64.rpm && rm mbedtls-2.7.5-1.el7.x86_64.rpm && \
    ln -s /lib64/libmbedcrypto.so.1 /lib64/libmbedcrypto.so.0 && \
    yum install -y shadowsocks-libev

ENV SERVER_ADDR 0.0.0.0
ENV SERVER_PORT 3128
ENV METHOD      chacha20-ietf-poly1305
ENV PASSWORD    #MyPassword#
ENV TIMEOUT     60

EXPOSE $SERVER_PORT/tcp
EXPOSE $SERVER_PORT/udp

CMD ss-server -s "$SERVER_ADDR" \
              -p "$SERVER_PORT" \
              -m "$METHOD"      \
              -k "$PASSWORD"    \
              -t "$TIMEOUT"     \
              -u
