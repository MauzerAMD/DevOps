# build app
FROM maven:3.8.6-openjdk-11 AS build
WORKDIR /app
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git .
RUN mvn clean package -DskipTests

# run app
FROM tomcat:9.0-jre11-openjdk-slim
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean
COPY --from=build /app/target/hello-1.0.war /usr/local/tomcat/webapps/ROOT.war
# app healthcheck
HEALTHCHECK --interval=30s --timeout=3s \
  CMD curl -f http://localhost:8080/ || exit 1
EXPOSE 8080
CMD ["catalina.sh", "run"]