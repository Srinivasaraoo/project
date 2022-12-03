FROM openjdk:8
LABEL author="kothapally rakesh"
LABEL organisation="KMR SCAFFOLDING"
ENV path="/springpetclinic.jar"
ARG WORKDIR='/spc'
ARG URL
RUN mkdir ${WORKDIR}
WORKDIR ${WORKDIR}
ADD ${URL} ${path}
EXPOSE 8080
CMD [ "java", "-jar", ${path} ]