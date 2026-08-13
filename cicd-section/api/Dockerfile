FROM gradle:jdk21 AS build
WORKDIR /app
COPY . /app
RUN chmod +x ./gradlew && chmod +x ./gradlew build

FROM openjdk:21-rc-jdk
COPY --from=build /app/build/libs/my-app-0.0.1-SNAPSHOT.jar ./my-app.jar
CMD [ "java", "-jar", "my-app.jar" ]
