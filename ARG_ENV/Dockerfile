FROM openjdk:11
LABEL author="kothapally rakesh"
LABEL organisaton="KMR SCAFFOLDING"
ENV PATH='/springpetclinic.jar'
ARG URL
ADD ${URL} ${PATH}
EXPOSE 8080
CMD [ "java", "-jar", ${PATH} "--host", "0.0.0.0" ] 