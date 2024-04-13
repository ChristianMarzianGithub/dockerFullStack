FROM openjdk:17-jdk-slim

WORKDIR /app

COPY helloWorldApi.jar /app/helloWorldApi.jar

COPY application.properties /app/application.properties
     
ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=sampleDatabase
ENV MYSQL_USER=rootUser
ENV MYSQL_PASSWORD=rootPassword
ENV MYSQL_PORT=3306

EXPOSE 8080

CMD ["java", "-jar", "helloWorldApi.jar"]