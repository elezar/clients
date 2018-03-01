FROM ubuntu:16.04

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        curl \
        default-jre \
        dnsutils \
        software-properties-common \
        unzip \
        wget \
    && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENV HADOOP_VERSION=2.6.0-cdh5.9.1
RUN wget https://downloads.mesosphere.com/hdfs/assets/hadoop-${HADOOP_VERSION}-dcos.tar.gz && \
    tar xf hadoop-${HADOOP_VERSION}-dcos.tar.gz && \
    rm hadoop-${HADOOP_VERSION}-dcos.tar.gz

COPY configure-hdfs.sh /configure-hdfs.sh
RUN chmod +x configure-hdfs.sh
ENV HDFS_SERVICE_NAME hdfs
ENV JAVA_HOME /usr/lib/jvm/default-java
RUN echo "/configure-hdfs.sh" >> ~/.bashrc
WORKDIR /hadoop-${HADOOP_VERSION}
