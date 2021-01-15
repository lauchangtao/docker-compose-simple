FROM openjdk:8-jdk-alpine
VOLUME /tmp
COPY ./lib/*.jar app.jar
EXPOSE 8080
RUN echo -e "https://mirror.tuna.tsinghua.edu.cn/alpine/v3.4/main\n\
https://mirror.tuna.tsinghua.edu.cn/alpine/v3.4/community" > /etc/apk/repositories
RUN apk --update add curl bash ttf-dejavu && \
      rm -rf /var/cache/apk/*
ENTRYPOINT [ "java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar" ]

#FROM openjdk:8-jdk-alpine
#ENV JAVA_OPTS -Duser.timezone=GMT+08
#COPY ./version /data/
#ADD ./localtime /etc/
#ADD ./timezone /etc/
#RUN date >> /data/version
#RUN mkdir -p /data/jar && mkdir -p /data/tracing
#VOLUME /data
#EXPOSE 9000
#ARG JAR_FILE=target/tracing-portal-1.0.0.jar
#COPY ${JAR_FILE} /data/jar/tracing-portal-1.0.0.jar
#ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/data/jar/tracing-portal-1.0.0.jar"]