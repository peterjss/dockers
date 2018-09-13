# using alpine-glibc instead of alpine  is mainly because JDK relies on glibc
#FROM docker.io/jeanblanchard/alpine-glibc
FROM centos

# author
MAINTAINER scc <peter.li@cygia.com>

# A streamlined jre
ADD jre8.tar.gz /usr/java/jre/

# set env
ENV JAVA_HOME /usr/java/jre
ENV PATH ${PATH}:${JAVA_HOME}/bin



# set apollo
RUN yum -y install wget
RUN wget http://mirrors.tuna.tsinghua.edu.cn/apache/activemq/activemq-apollo/1.7.1/apache-apollo-1.7.1-unix-distro.tar.gz
RUN tar xzvf apache-apollo-1.7.1-unix-distro.tar.gz
RUN rm -rf apache-apollo-1.7.1-unix-distro.tar.gz
RUN mv apache-apollo-1.7.1 /usr/apollo

# run container with base path:/opt
WORKDIR /opt

# set broker
RUN /usr/apollo/bin/apollo create mybroker

# start the apollo broker 'mybroker'
CMD /opt/mybroker/bin/apollo-broker run

# INFO  | Accepting connections at: tcp://0.0.0.0:61613
# INFO  | Accepting connections at: tls://0.0.0.0:61614
# INFO  | Accepting connections at: ws://0.0.0.0:61623/
# INFO  | Accepting connections at: wss://0.0.0.0:61624/
# INFO  | Administration interface available at: https://127.0.0.1:61681/
# INFO  | Administration interface available at: http://127.0.0.1:61680/

EXPOSE 61613
EXPOSE 61614
EXPOSE 61623
EXPOSE 61624
EXPOSE 61681
EXPOSE 61680
