FROM maven:3.5.3-jdk-8-alpine as builder
WORKDIR /usr/src/app
COPY pom.xml /usr/src/app/pom.xml
RUN mvn dependency:go-offline
COPY src/ /usr/src/app/src/
RUN mvn clean package

# Final image
FROM java:openjdk-8u111-jre
COPY --from=builder /usr/src/app/target/fakecoin-1.0.jar /usr/src/app/app.jar
EXPOSE 8080
CMD ["java", "-jar", "/usr/src/app/app.jar"]