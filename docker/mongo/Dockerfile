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

