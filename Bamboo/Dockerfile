FROM ubuntu
MAINTAINER blubber:alex

RUN apt-get update -y
RUN apt-get install default-jdk wget -y
RUN wget -q -O /opt/ https://www.atlassian.com/software/bamboo/downloads/binary/atlassian-bamboo-5.14.0.2.tar.gz

WORKDIR /opt/
RUN tar -xzf atlassian-bamboo-5.14.0.2.tar.gz
RUN mkdir bamboo-home

WORKDIR /opt/atlassian-bamboo-5.14.0.2/atlassian-bamboo/WEB-INF/classes/
RUN echo "bamboo.home= /opt/atlassian-bamboo-5.14.0.2/bamboo-home" >> bamboo-init.properties

EXPOSE 8085
WORKDIR /opt/atlassian-bamboo-5.14.0.2/
ENTRYPOINT bin/start-bamboo.sh && bash

