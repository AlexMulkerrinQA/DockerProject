FROM ubuntu
MAINTAINER blubber:alex

RUN apt-get update -y
RUN apt-get install wget -y
RUN wget -q -O /opt/jira.bin https://www.atlassian.com/software/jira/downloads/binary/atlassian-jira-software-7.2.3-x64.bin
RUN chmod +x /opt/jira.bin
ADD response.varfile /opt/response.varfile
RUN /opt/jira.bin -q -varfile /opt/response.varfile

EXPOSE 8080
ENTRYPOINT service jira start && bash

