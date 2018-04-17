FROM centos:7
MAINTAINER anexplore
ENV REFRESHED_AT 2018-04-18

ADD chrome.repo /etc/yum.repos.d/
RUN yum -y install unzip
RUN yum info google-chrome-stable && yum -y install google-chrome-stable
RUN yum install -y mesa-libOSMesa mesa-libOSMesa-devel gnu-free-sans-fonts
RUN yum install -y ipa-gothic-fonts ipa-pgothic-fonts wqy-zenhei-fonts
RUN ln -s /usr/lib64/libOSMesa.so.8.0.0 /opt/google/chrome/libosmesa.so
RUN mkdir -p /home/software/ && wget https://chromedriver.storage.googleapis.com/2.37/chromedriver_linux64.zip -O /home/software/chromedriver_linux64.zip && cd /home/software/ && unzip chromedriver_linux64.zip && rm -rf chromedriver_linux64.zip && cd -
