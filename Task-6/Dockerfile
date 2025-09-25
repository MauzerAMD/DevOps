FROM ubuntu:18.04
RUN apt update
RUN apt install default-jdk tomcat9 maven git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /boxfuse-sample-java-war-hello/
RUN mvn package
RUN cp /boxfuse-sample-java-war-hello/target/hello-1.0.war /var/lib/tomcat9/webapps/
EXPOSE 8080
CMD ["java", "hello-1.0.war"]