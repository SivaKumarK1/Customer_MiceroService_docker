#FROM maven:3.8.4-jdk-11
#CMD ["mvn", "clean", "install"]
#ENTRYPOINT ["java","-jar","./target/user_service-0.0.1-SNAPSHOT.jar"]
##COPY target/user_service-0.0.1-SNAPSHOT.jar userapp.jar
##ENTRYPOINT ["java","-jar","userapp.jar"]


# Build stage
FROM maven:3.6.0-jdk-11-slim AS build
EXPOSE 8082
WORKDIR /user_service
COPY . /user_service/.
RUN mvn clean package
ENTRYPOINT ["java","-jar","./contact_service/target/user_service-0.0.1-SNAPSHOT.jar"]

 


# FROM openjdk:11
# EXPOSE 8081
# #ADD ./target/user_service-0.0.1-SNAPSHOT.jar userapp.jar
# COPY [ "./target/user_service-0.0.1-SNAPSHOT.jar", "userapp.jar" ]
# ENTRYPOINT [ "java", "-jar", "userapp.jar" ]
