FROM ubuntu:18.04

RUN apt-get update --fix-missing

RUN apt-get install build-essential autoconf libtool pkg-config libboost-all-dev libssl-dev libprotobuf-dev protobuf-compiler libevent-dev libqt4-dev libcanberra-gtk-module libdb-dev libdb++-dev bsdmainutils -y

RUN apt-get -y install git

RUN git clone https://github.com/bitcoin/bitcoin.git

WORKDIR bitcoin

RUN ./autogen.sh
RUN ./configure --with-incompatible-bdb
RUN make
RUN make install
RUN mkdir -p /root/bitcoind-simnet/