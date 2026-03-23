FROM maven:3.9.9-eclipse-temurin-17 AS build

WORKDIR /app

COPY pom.xml ./
RUN mvn dependency:go-offline

COPY src ./src
RUN mvn package

FROM eclipse-temurin:17-jre

WORKDIR /app

COPY --from=build /app/target /app/target

CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "target/words.jar"]
