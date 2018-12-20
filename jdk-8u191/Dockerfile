FROM centos:7

MAINTAINER Tiago Oliveira <tiagoliveiraf@gmail.com>

ENV JAVA_HOME /usr/java/jdk
ENV PATH $PATH:/usr/java/jdk/bin


RUN yum update -y && \
    yum install wget -y && \
    wget http://192.168.254.133/jdk-8u191-linux-x64.tar.gz && \
    tar -vzxf jdk-8u191-linux-x64.tar.gz && \
    rm -rf jdk-8u191-linux-x64.tar.gz && \
    mkdir /usr/java && \
    mv jdk1.8.0_191/ /usr/java/jdk && \
    yum remove wget -y && \
    yum clean all && \
    rm -rf /var/cache/yum && rm -rf /tmp/* 
    

