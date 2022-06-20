FROM registry.access.redhat.com/redhat-openjdk-18/openjdk18-openshift:1.12-1.1655301789
WORKDIR /src/
COPY passwordapi.jar /src/
EXPOSE 8080
CMD ["java", "-jar", "/src/passwordapi.jar"]