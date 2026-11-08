FROM maven:3.9.9-eclipse-temurin-21 AS builder

WORKDIR /app

COPY pom.xml .

RUN mvn dependency:go-offline

COPY src ./src

RUN mvn clean package -Dmaven.test.skip=true

# Extraer el JAR generado
CMD ["sh", "-c", "cp target/*.jar /output/app.jar"]