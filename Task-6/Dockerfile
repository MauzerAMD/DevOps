# build
FROM maven:3-jdk-11 as build
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /boxfuse-sample-java-war-hello/
RUN mvn package
#
# run tomcat
FROM tomcat:latest
RUN rm -rf /usr/local/tomcat/webapps/
COPY --from=build /boxfuse-sample-java-war-hello/target/hello-1.0.war /var/lib/tomcat9/webapps/
EXPOSE 8080