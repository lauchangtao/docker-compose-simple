FROM openjdk:8-jdk-alpine
VOLUME /tmp
COPY myapp.jar app.jar
ENTRYPOINT [ "java","-agentlib:jdwp=transport=dt_socket,server=y,address=8080,suspend=n","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar" ]
