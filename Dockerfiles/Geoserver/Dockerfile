FROM mcpayment/ubuntu1404
MAINTAINER Hugo Baltz <hugo.baltz@gmail.com>

RUN  export DEBIAN_FRONTEND=noninteractive
ENV DEBIAN_FRONTEND noninteractive

ENV http_proxy http://10.0.4.2:3128
ENV https_proxy https://10.0.4.2:3128

ENV GS_VERSION 2.10.1
ENV GEOSERVER_DATA_DIR /opt/geoserver/data_dir

RUN mkdir -p $GEOSERVER_DATA_DIR && mkdir geoserver/

RUN apt-get update -y && \
    apt-get install -y software-properties-common && \ 
    apt-add-repository ppa:webupd8team/java && \
    apt-get update -y && \
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 && \
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-get install -y oracle-java8-installer && \
    apt-get install -y oracle-java8-unlimited-jce-policy && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /var/cache/oracle-jdk8-installer

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

ADD https://downloads.sourceforge.net/project/geoserver/GeoServer/2.10.1/geoserver-2.10.1-bin.zip?r=http%3A%2F%2Fgeoserver.org%2Frelease%2Fstable%2F&ts=1487150943&use_mirror=vorboss geoserver/

RUN unzip geoserver/geoserver-2.10.1-bin.zip -d /opt/geoserver/ && echo "export GEOSERVER_HOME=/opt/geoserver" >> ~/.profile  && chmod +x /opt/geoserver/bin/startup.sh

EXPOSE 8080
CMD /opt/geoserver/geoserver-2.10.1/bin/startup.sh