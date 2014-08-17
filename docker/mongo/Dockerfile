##
# Dockerfile with Ububtu 14.10 - utopic
# MongoDB 2.6
# Docker image venturus/mongo

FROM ubuntu:14.10
MAINTAINER Paulo Sigrist <paulo.sigrist@venturus.org.br>

RUN echo "deb http://archive.ubuntu.com/ubuntu utopic main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

#  MongoDB 2.6
RUN apt-get install mongodb -y

# Expose Mongo ports
EXPOSE 27017
EXPOSE 28017

# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

# Entry point
ENTRYPOINT ["/usr/bin/mongod"]

# Default parameters
CMD ["--help"]

#####
# Using this image:
#
# Default (mongod --help)
# $ docker run venturus/mongodb
#
# Run mongodb (
# $ docker run -p venturus/mongodb -v
#
# Run mon
# $ docker run -p 8080:8080 -p 9990:9990 -d venturus/jboss:7.1.1-Final --server-config=standalone-full.xml
#
# To login into the image
# $ docker run -ti --entrypoint="/bin/bash" venturus/mongodb -s


