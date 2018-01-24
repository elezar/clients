FROM nvaziri/hdfs-client:dev


RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        curl \
        unzip \
    && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
