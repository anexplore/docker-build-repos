FROM centos:7
MAINTAINER anexplore
ENV REFRESH_AT 2018-04-27

RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash -
RUN yum -y install nodejs
RUN npm install -g cnpm --registry=https://registry.npm.taobao.org
RUN cnpm install -g anyproxy
RUN cnpm install -g react@^15.0.0
RUN echo "Y" |anyproxy-ca && cp ~/.anyproxy/certificates/rootCA.crt /etc/pki/ca-trust/source/anchors/ \
     && update-ca-trust 
EXPOSE 8001 8002
ENTRYPOINT anyproxy
