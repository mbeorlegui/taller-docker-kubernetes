FROM openjdk:11.0-slim
USER root
WORKDIR /src
COPY passwordapi.jar /src/
EXPOSE 8080
CMD ["java", "-jar", "/src/passwordapi.jar"]