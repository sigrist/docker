##
# Dockerfile with Ububtu 14.10 - utopic
# Oracle Java JDK 7
# Docker image venturus/jdk7
FROM venturus/jdk
MAINTAINER Paulo Sigrist <paulo.sigrist@venturus.org.br>

# Download JBoss 7.1.1
RUN mkdir -p /opt
RUN cd /opt
RUN wget "http://download.jboss.org/jbossas/7.1/jboss-as-7.1.1.Final/jboss-as-7.1.1.Final.tar.gz" 
RUN tar -zxvf jboss-as-7.1.1.Final.tar.gz

# Expose JBoss ports
EXPOSE 8080
EXPOSE 9990

# Entry point
ENTRYPOINT ["/opt/jboss-as-7.1.1.Final/bin/standalone.sh"]

# Default parameters
CMD ["-b 0.0.0.0 -bmanagement 0.0.0.0"]

#####
# Using this image:
#
# Default (start jboss using standalone.xml file binding with ip 0.0.0.0)
# $ docker run -p 8080:8080 -p 9990:9990 venturus/jdk7_jboss7 
#
# Specify a custom config file
# $ docker run venturus/jdk7_jboss7 --server-config=standalone-full.xml
#
# To run and free the console, run with -d parameter
# $ docker run -p 8080:8080 -p 9990:9990 -d venturus/jdk7_jboss7 --server-config=standalone-full.xml
#
#
# For more details which parameters to use, check https://docs.jboss.org/author/display/AS71/Command+line+parameters
