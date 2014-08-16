##
# Dockerfile with Ububtu 14.10 - utopic
# Oracle Java JDK 7
# Docker image venturus/jdk
FROM venturus/jdk
MAINTAINER Paulo Sigrist <paulo.sigrist@venturus.org.br>

# Download JBoss 7.1.1 (based on jdk7_jboss7/Dockerfile from codenvy)
RUN mkdir /opt/jboss && \
    wget \
    -qO- \
    "http://download.jboss.org/jbossas/7.1/jboss-as-7.1.1.Final/jboss-as-7.1.1.Final.tar.gz" | tar -zx --strip-components=1 -C /opt/jboss/ 

# Expose JBoss ports
EXPOSE 8009
EXPOSE 8080
EXPOSE 9990

# Entry point
ENTRYPOINT ["/opt/jboss/bin/standalone.sh"]

# Default parameters
CMD ["-b 0.0.0.0 -bmanagement 0.0.0.0"]

#####
# Using this image:
#
# Default (start jboss using standalone.xml file binding with ip 0.0.0.0)
# $ docker run -p 8080:8080 -p 9990:9990 venturus/jboss:7.1.1-Final
#
# Specify a custom config file
# $ docker run venturus/jboss:7.1.1-Final --server-config=standalone-full.xml
#
# To run and free the console, run with -d parameter
# $ docker run -p 8080:8080 -p 9990:9990 -d venturus/jboss:7.1.1-Final --server-config=standalone-full.xml
#
# To login into the image
# $ docker run -ti --entrypoint="/bin/bash" venturus/jboss:7.1.1-Final -s
# For more details which parameters to use, check https://docs.jboss.org/author/display/AS71/Command+line+parameters
