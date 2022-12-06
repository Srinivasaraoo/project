FROM ubuntu:18.04
LABEL author="Rakesh"
LABEL maintainer="Rakesh"
RUN apt update && apt install openjdk-8-jdk wget -y
RUN wget https://referenceapplicationskhaja.s3.us-west-2.amazonaws.com/spring-petclinic-2.4.2.jar
EXPOSE 8080
CMD [ "java",  "-jar",  "spring-petclinic-2.4.2.jar" ]