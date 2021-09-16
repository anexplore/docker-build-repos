FROM centos:7

RUN yum -y install epel-release && yum -y install tor && yum -y install privoxy
RUN echo "SOCKSPort 0.0.0.0:9050" >> /etc/tor/torrc && \
    echo "forward-socks5t   /               127.0.0.1:9050 ." >> /etc/privoxy/config && \
    sed -i 's/listen-address  127.0.0.1:8118/listen-address  0.0.0.0:8118/g' /etc/privoxy/config

EXPOSE 9050
EXPOSE 8118

CMD chown root:root /run/tor &&  tor --runasdaemon 1 &&  privoxy /etc/privoxy/config && /bin/bash
