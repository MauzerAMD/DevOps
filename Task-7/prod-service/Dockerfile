FROM tomcat:9.0-jre11-openjdk-slim
RUN rm -rf /usr/local/tomcat/webapps/*
VOLUME /input
CMD cp /input/hello-1.0.war /usr/local/tomcat/webapps/ROOT.war && \
   catalina.sh run