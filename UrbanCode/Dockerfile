FROM ubuntu
MAINTAINER blubber:alex

RUN apt-get update -y
RUN apt-get install openjdk7-jre -y
COPY ibm-ucd-install /installer/
COPY install.extra.properties /installer/

WORKDIR /installer/ibm-ucd-install
RUN cat install.extra.properties >> install.properties
RUN install-server.sh

VOLUME /opt/ibm-ucd/server/var/repository
VOLUME /opt/ibm-ucd/server/appdata/var/db


EXPOSE 8080 8443
ENTRYPOINT /opt/ibm-ucd/server/bin/server run && bash

