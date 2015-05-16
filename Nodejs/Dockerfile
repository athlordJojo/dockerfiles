FROM resin/rpi-raspbian:jessie
MAINTAINER the native web <hello@thenativeweb.io>

RUN apt-get update && \
    apt-get install -y build-essential git libssl-dev python wget

RUN wget http://nodejs.org/dist/v0.12.2/node-v0.12.2.tar.gz && \
    tar -xvzf node-v0.12.2.tar.gz && \
    rm node-v0.12.2.tar.gz

WORKDIR /node-v0.12.2
RUN sudo ./configure
RUN sudo make -j4
RUN sudo make install
RUN sudo mkdir /application
WORKDIR /application
run rm -r /node-v0.12.2
EXPOSE 5000
