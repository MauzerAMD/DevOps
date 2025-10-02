FROM maven:3.8.6-openjdk-11 AS builder
WORKDIR /app
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git . && \
    mvn clean package -DskipTests
VOLUME /output
WORKDIR /output
CMD cp /app/target/hello-1.0.war /output/hello-1.0.war && \
    echo "Build completed! WAR file is available in /output directory"