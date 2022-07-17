#FROM maven:3.8.4-jdk-11
#CMD ["mvn", "clean", "install"]
#ENTRYPOINT ["java","-jar","./target/user_service-0.0.1-SNAPSHOT.jar"]
##COPY target/user_service-0.0.1-SNAPSHOT.jar userapp.jar
##ENTRYPOINT ["java","-jar","userapp.jar"]


# Build stage
 FROM maven:3.6.0-jdk-11-slim AS build
 WORKDIR .
 COPY ./user_service/src /home/app/src
 COPY ./user_service/pom.xml /home/app
 RUN mvn -f /home/app/pom.xml verify clean package --fail-never

# RUN #mvn -f /home/app/pom.xml   package

# # Package stage
FROM openjdk:11-jre-slim
COPY --from=build /home/app/target/user_service-0.0.1-SNAPSHOT.jar /usr/local/lib/userservice.jar
EXPOSE 8081
ENTRYPOINT ["java","-jar","/usr/local/lib/userservice.jar"]

# FROM openjdk:11
# EXPOSE 8081
# #ADD ./target/user_service-0.0.1-SNAPSHOT.jar userapp.jar
# COPY [ "./target/user_service-0.0.1-SNAPSHOT.jar", "userapp.jar" ]
# ENTRYPOINT [ "java", "-jar", "userapp.jar" ]
