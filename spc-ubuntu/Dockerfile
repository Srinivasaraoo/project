FROM ubuntu:18.04
RUN apt update && apt install openjdk-11-jdk -y && apt install wget -y
RUN wget https://github.com/rakesh914327/devops/blob/master/spring-petclinic-2.7.3.jar
CMD java -jar spring-petclinic-2.7.3.jar