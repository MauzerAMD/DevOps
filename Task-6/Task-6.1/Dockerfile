FROM tomcat:9.0-jdk11-openjdk
RUN apt-get update && apt-get install -y curl
RUN curl -L -o /usr/local/tomcat/webapps/ROOT.war \
    https://github.com/boxfuse/boxfuse-sample-java-war-hello/releases/download/v1.0/hello-1.0.war
EXPOSE 8080
CMD ["catalina.sh", "run"]