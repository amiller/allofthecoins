FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install -qy build-essential
RUN apt-get install -qy libboost-all-dev
RUN apt-get install -qy git libssl-dev libdb++-dev libdb-dev libminiupnpc-dev
RUN apt-get install -qy autoconf
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN git clone https://github.com/bitcoin/bitcoin
WORKDIR bitcoin
CMD bash

RUN ./autogen.sh
RUN ./configure
RUN ./make

# ADD bitcoin.conf /root/.bitcoin/bitcoin.conf
# CMD ./bitcoind -debug
