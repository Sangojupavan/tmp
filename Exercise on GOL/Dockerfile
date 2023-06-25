FROM amazoncorretto:17-al2023-jdk
LABEL Author="pavan" organigation="ssgc" 
ADD target/spring-petclinic-3.1.0-SNAPSHOT.jar /spring-petclinic.jar 
EXPOSE 8080
CMD [ "java", "-jar", "/spring-petclinic.jar" ]