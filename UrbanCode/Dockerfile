FROM ubuntu:14.04
#FROM ibmcom/ibm-java, just do that inline
ADD ibm-java-x86_64-71 /opt/java/ibm-java-x86_64-71
ENV JAVA_HOME=/opt/java/ibm-java-x86_64-71/jre
ENV PATH=/opt/java/ibm-java-x86_64-71/jre/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

#MAINTAINER Zachary Jaffee <zjaffee@us.ibm.com> original source
MAINTAINER blubber:alex

# get curl, unzip, less
RUN apt-get update -qq \
  && apt-get --no-install-recommends install -qq curl unzip > /dev/null \
  && apt-get install less \
  && rm -rf /var/lib/apt/lists/*

#ENV UCD_SERVER ibm-ucd-6.1.1.7
ENV UCD_SERVER IBM_UCD_SERVER_6.1.1.5
ENV UCD_SERVER_ZIP $UCD_SERVER.zip
ENV IBM_UCD_SECURE true
ENV CERTS_DIR /certs.d
ENV LICENSE=accept

WORKDIR /opt/ibm-ucd/server

# The server state is persisted in this volume
VOLUME /opt/ibm-ucd/server/var
VOLUME $CERTS_DIR

# http: 8080 https: 8443 jms: 7918
EXPOSE 8080 8443 7918

ADD $UCD_SERVER_ZIP /$UCD_SERVER_ZIP
COPY installtools /installtools
COPY setup_certs.sh /

RUN /installtools/install_ucd.sh $UCD_SERVER_ZIP
RUN mkdir -p /

# by default run the ucd server command with the run option
COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
CMD ["server", "run"]


