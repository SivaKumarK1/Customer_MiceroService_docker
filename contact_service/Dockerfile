#FROM maven:3.8.4-jdk-11
#CMD ["mvn", "clean", "install"]
##COPY target/contact_service-0.0.1-SNAPSHOT.jar contactapp.jar
#ENTRYPOINT ["java","-jar","target/contact_service-0.0.1-SNAPSHOT.jar"]
#FROM maven:3.8.4-jdk-11
#CMD ["mvn", "clean", "install"]
#ENTRYPOINT ["java","-jar","./target/user_service-0.0.1-SNAPSHOT.jar"]
##COPY target/user_service-0.0.1-SNAPSHOT.jar userapp.jar
##ENTRYPOINT ["java","-jar","userapp.jar"]

#  Build stage
#  
FROM maven:3.6.0-jdk-11-slim AS build
EXPOSE 8082
WORKDIR /contact_service
COPY . /contact_service/.
RUN mvn clean package
ENTRYPOINT ["java","-jar","./contact_service/target/contact_service-0.0.1-SNAPSHOT.jar"]

# Package stage
#
#  FROM openjdk:11-jre-slim
#  COPY --from=build /home/app/target/contact_service-0.0.1-SNAPSHOT.jar /usr/local/lib/contactservice.jar
#  EXPOSE 8082
#  ENTRYPOINT ["java","-jar","/usr/local/lib/contactservice.jar"]

#FROM openjdk:11

# FROM openjdk:11-jre-slim
# EXPOSE 8082
# #ADD  target/contact_service-0.0.1-SNAPSHOT.jar contactapp.jar
# COPY [ "./target/contact_service-0.0.1-SNAPSHOT.jar", "contactapp.jar" ]
# ENTRYPOINT [ "java", "-jar", "contactapp.jar" ]
