
FROM centos:6.9
MAINTAINER anexplore
ENV REFRESHED_AT 2018-04-18

RUN yum -y install epel-release && yum -y install tor && yum -y install privoxy
RUN echo "SOCKSPort 9050" >> /etc/tor/torrc && \
    echo "forward-socks5t   /               127.0.0.1:9050 ." >> /etc/privoxy/config

EXPOSE 9050
EXPOSE 8118

CMD service tor start &&  service privoxy start && /bin/bash
