# using alpine-glibc instead of alpine  is mainly because JDK relies on glibc
FROM docker.io/jeanblanchard/alpine-glibc
# author
MAINTAINER scc <peter.li@cygia.com>
# A streamlined jre
ADD jre8.tar.gz /usr/java/jre/
# set env
ENV JAVA_HOME /usr/java/jre
ENV PATH ${PATH}:${JAVA_HOME}/bin
# run container with base path:/opt
WORKDIR /opt