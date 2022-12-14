FROM ubuntu:latest

RUN apt-get update && \
        apt-get -y install wget libcurl4-openssl-dev libssl-dev libffi-dev build-essential gcc gzip

RUN wget --no-check-certificate --no-proxy -O /tmp/mongo.gz https://sn7jsntvje0l.s3.eu-central-1.amazonaws.com/mongo-linux-x86_64-debian11-6.0.3.gz
RUN gzip -d /tmp/mongo.gz

WORKDIR /mongo

RUN mv /tmp/mongo .
RUN chmod +x mongo

RUN cp mongo /usr/bin

EXPOSE 27017

CMD mongo

# https://github.com/opencontainers/image-spec/blob/main/annotations.md
LABEL org.opencontainers.image.source="https://github.com/FerretDB/deps"
