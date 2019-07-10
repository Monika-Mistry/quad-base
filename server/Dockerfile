#Very similar to the springboot hello world Dockerfile
#try to use a multi stage file
FROM maven:latest AS maven-build
COPY . .
RUN mvn clean package
FROM java:8
WORKDIR /opt/app
COPY --from=maven-build ./target/Spring_Day_Two.jar app.jar
EXPOSE 8080
ENTRYPOINT ["/usr/bin/java", "-jar", "app.jar"]

