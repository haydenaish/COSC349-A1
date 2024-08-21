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

# Expose 8080
EXPOSE 8080

# Command to run the application
ENTRYPOINT ["./gradlew", "run"]
