FROM ubuntu:14.04

RUN apt-get update && apt-get install -qy git 
RUN apt-get install -qy build-essential
RUN apt-get install -qy libboost-all-dev
RUN apt-get install -qy libssl-dev libdb++-dev libdb-dev libminiupnpc-dev
RUN apt-get install -qy autoconf libtool pkg-config bsdmainutils libevent-dev
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN git clone https://github.com/bitcoin/bitcoin
WORKDIR bitcoin

RUN ./autogen.sh
RUN ./configure --with-incompatible-bdb
RUN make

EXPOSE 18333
VOLUME /root/.bitcoin

ADD bitcoin.conf /root/.bitcoin/bitcoin.conf
CMD ./src/bitcoind -server -debug -testnet
