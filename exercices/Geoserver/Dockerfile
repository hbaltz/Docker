FROM mcpayment/ubuntu1404
MAINTAINER Hugo Baltz <hugo.baltz@gmail.com>

# Expose le port 8080
EXPOSE 8080

# Pour le apt-get
ENV http_proxy http://10.0.4.2:3128
ENV https_proxy https://10.0.4.2:3128

# Installation java :
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

# Installation geoserver
ARG GS_VERSION=2.10.1
ENV GEOSERVER_DATA_DIR /opt/geoserver/data_dir
VOLUME opt/geoserver/geoserver-${GS_VERSION}/data_dir

ADD https://downloads.sourceforge.net/project/geoserver/GeoServer/${GS_VERSION}/geoserver-${GS_VERSION}-bin.zip?r=http%3A%2F%2Fgeoserver.org%2Frelease%2Fstable%2F&ts=1487150943&use_mirror=vorboss geoserver/

RUN unzip geoserver/geoserver-${GS_VERSION}-bin.zip -d /opt/geoserver/ && echo "export GEOSERVER_HOME=/opt/geoserver" >> ~/.profile  && chmod +x /opt/geoserver/geoserver-${GS_VERSION}/bin/startup.sh && rm -R geoserver/geoserver-${GS_VERSION}-bin.zip

CMD /opt/geoserver/geoserver-${GS_VERSION}/bin/startup.sh