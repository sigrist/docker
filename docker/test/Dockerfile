##
# Dockerfile with Ububtu 14.10 - utopic
# Oracle Java JDK 7
# Docker image venturus/jdk7

FROM venturus/jdk7_jboss7
# Expose JBoss ports
EXPOSE 8080
EXPOSE 9990

# Entry point
ENTRYPOINT ["/opt/jboss-as-7.1.1.Final/bin/standalone.sh"]

# Defaut parameters
CMD ["-b 0.0.0.0 -bmanagement 0.0.0.0"]