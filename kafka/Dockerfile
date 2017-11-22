FROM confluentinc/cp-kafka

RUN apt-get update && \
    apt-get install --no-install-recommends -y \
        unzip

ADD resources/jre-8u152-linux-x64-jce-unlimited.tar.gz /opt

ENV JAVA_HOME /opt/jre1.8.0_152

ADD resources/0.30.3/bootstrap.zip /opt
RUN cd /opt && \
	unzip bootstrap.zip && \
	rm bootstrap.zip

ENV KAFKA_CONFIG_ROOT /tmp/kafkaconfig
RUN mkdir -p $KAFKA_CONFIG_ROOT

COPY client-jaas.conf ${KAFKA_CONFIG_ROOT}
COPY client.properties ${KAFKA_CONFIG_ROOT}
COPY krb5.conf ${KAFKA_CONFIG_ROOT}


COPY start.sh ${KAFKA_CONFIG_ROOT}

CMD ${KAFKA_CONFIG_ROOT}/start.sh
