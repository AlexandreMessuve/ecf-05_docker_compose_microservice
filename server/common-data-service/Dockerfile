FROM maven:3.8-openjdk-11-slim AS builder

WORKDIR /app

COPY pom.xml .

RUN mvn dependency:go-offline

COPY src ./src

RUN mvn clean package -DskipTests

FROM openjdk:11-jre-slim

COPY --from=builder /app/target/*.jar /common-data-service.jar

LABEL authors="alexandre.messuves@gmail.com"

ENTRYPOINT ["java", "-jar", "common-data-service.jar"]