FROM ubuntu:14.04
MAINTAINER blubber:alex

RUN apt-get update -y
RUN apt-get install wget -y
RUN wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | apt-key add -
RUN sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
RUN apt-get update -y
RUN apt-get install jenkins -y

# packages for setting up builds on Jenkins
RUN apt-get install git maven openjdk-7-jdk -y

EXPOSE 8080
ENTRYPOINT service jenkins start && bash

