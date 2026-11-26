FROM maven:3.9.6-eclipse-temurin-21 AS build
WORKDIR /app
COPY . .
RUN mvn -q clean package -DskipTests

FROM eclipse-temurin:21-jdk-alpine
WORKDIR /app
COPY --from=build /app/presentacion/target/apicalendario.jar app.jar
EXPOSE 8081
CMD ["java", "-jar", "app.jar"]
