FROM openjdk:8-jre-alpine
RUN apk update ;\
apk add --no-cache curl

WORKDIR /usr/local/jetty/
RUN curl -L "https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.4.39.v20210325/jetty-distribution-9.4.39.v20210325.tar.gz" -o jetty.tar.gz ;\
tar  -xvf jetty.tar.gz ;\
cp -R jetty-distribution-9.4.39.v20210325/* . ;\
rm -R jetty-distribution-9.4.39.v20210325/    ;\
#rm -R /usr/local/jetty/demo-base/webapps/* ;\
rm  jetty.tar.gz

RUN apk del curl

WORKDIR /usr/local/jetty/demo-base/
EXPOSE 8080
CMD java -jar /usr/local/jetty/start.jar



