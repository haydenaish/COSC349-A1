# Use an official Gradle image as a base
FROM gradle:7.5-jdk17 AS builder

# Set the working directory
WORKDIR /app

# Copy the Gradle wrapper and build scripts
COPY gradlew /app/gradlew
COPY gradle /app/gradle
COPY build.gradle /app/build.gradle

# Copy the rest of the application code
COPY src /app/src

# Make the Gradle wrapper executable
RUN chmod +x /app/gradlew

# Create fatJar
RUN ./gradlew fatJar 

# Stage 2: Runtime image
FROM openjdk:17-jdk-slim

WORKDIR /app

COPY --from=builder /app/build/libs libs/

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/app/libs/backend-fat.jar"]