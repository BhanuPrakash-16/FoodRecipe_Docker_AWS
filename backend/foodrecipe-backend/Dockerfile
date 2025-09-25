# Stage 1: Build with Maven
FROM eclipse-temurin:21-jdk AS build
WORKDIR /app
COPY . .
RUN ./mvnw clean package -DskipTests

# Stage 2: Run the JAR
FROM eclipse-temurin:21-jdk
WORKDIR /app
COPY --from=build /app/target/foodrecipie.jar app.jar
EXPOSE 8090
ENTRYPOINT ["java", "-jar", "app.jar"]
