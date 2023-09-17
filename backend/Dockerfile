FROM maven:3.8.6-jdk-11 AS builder
COPY . .
WORKDIR /ums-backend
RUN mvn package

FROM openjdk:11
WORKDIR /ums-backend
COPY --from=builder /ums-backend/target/ums-1.0.jar /ums-backend
CMD ["java", "-jar", "ums-1.0.jar"]
