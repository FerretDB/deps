FROM ubuntu:latest

RUN apt-get update && \
        apt-get -y install build-essential gcc git && \
        apt-get -y install libcurl4-openssl-dev libssl-dev libffi-dev liblzma-dev python3-pip

RUN git clone https://github.com/mongodb/mongo.git

WORKDIR /mongo

RUN python3 -m pip install -r etc/pip/compile-requirements.txt

# note we can use the -j1 parameter to use less memory during building
RUN python3 buildscripts/scons.py install-mongo

RUN mv build/install/bin/mongo /usr/bin

EXPOSE 27017

CMD mongo

# https://github.com/opencontainers/image-spec/blob/main/annotations.md
LABEL org.opencontainers.image.source="https://github.com/FerretDB/deps"
