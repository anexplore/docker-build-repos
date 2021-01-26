FROM centos:7
ENV REFRESHED_AT 2021-01-25

RUN yum -y install epel-release && yum -y install wget gcc make libevent-devel openssl-devel libzstd-devel zx-devel 
RUN cd /home && wget https://dist.torproject.org/tor-0.4.4.6.tar.gz && \
    tar xvzf tor-0.4.4.6.tar.gz && rm tor-0.4.4.6.tar.gz 
WORKDIR /home/tor-0.4.4.6
RUN ./configure --enable-lzma --enable-zstd && make -j && make install && \
	cp /usr/local/etc/tor/torrc.sample /usr/local/etc/tor/torrc

