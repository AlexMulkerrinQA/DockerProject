FROM ubuntu
MAINTAINER blubber:alex

WORKDIR /opt/
RUN apt-get update -y
RUN apt-get install wget -y
RUN apt-get install default-jdk -y
RUN wget -q -O nexus.tar http://download.sonatype.com/nexus/3/nexus-3.0.2-02-unix.tar.gz
RUN tar xvfz nexus.tar
ENV RUN_AS_USER=root

EXPOSE 8081
ENTRYPOINT nexus-3.0.2-02/bin/nexus start && bash

