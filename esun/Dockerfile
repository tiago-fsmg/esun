FROM tiagofsmg/jdk:8.191

MAINTAINER Tiago Oliveira <tiagoliveiraf@gmail.com>

ENV PATH $PATH:/usr/java/glassfish5/bin
ENV GALSSFISH_HOME /usr/java/glassfish5

COPY glassfish5.zip /glassfish5.zip
COPY esun.war /app/esun.war

RUN yum update -y && \
    yum install unzip -y && \
    unzip glassfish5.zip -d /usr/java/ && \
    chmod +x /usr/java/glassfish5/bin/asadmin && \
    rm -rf glassfish5.zip && \
    asadmin start-domain && \
    asadmin deploy /app/esun.war && \
    yum remove wget unzip -y && \
    yum clean all && \
    rm -rf /var/cache/yum && rm -rf /tmp/* 

EXPOSE 	8080 4848 8181 

CMD ["asadmin", "start-domain", "-v"]
