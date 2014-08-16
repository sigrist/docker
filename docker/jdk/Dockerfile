##
# Dockerfile with Ububtu 14.10 - utopic
# Oracle Java JDK 7
# Docker image venturus/jdk7

FROM ubuntu:14.10
MAINTAINER Paulo Sigrist <paulo.sigrist@venturus.org.br>

RUN echo "deb http://archive.ubuntu.com/ubuntu utopic main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

# Oracle JDK 7
RUN apt-get install software-properties-common -y
RUN apt-add-repository ppa:webupd8team/java -y
RUN apt-get update
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections
RUN apt-get install oracle-java7-installer -y