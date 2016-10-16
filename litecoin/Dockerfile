FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install -qy build-essential
RUN apt-get install -qy libboost-all-dev
RUN apt-get install -qy git libssl-dev libdb++-dev libdb-dev libminiupnpc-dev
RUN apt-get install -qy autoconf libtool pkg-config bsdmainutils libevent-dev
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN git clone https://github.com/litecoin-project/litecoin
WORKDIR litecoin
RUN git checkout 623f20b53ed305 # Work around because of https://github.com/litecoin-project/litecoin/issues/252


RUN ./autogen.sh
RUN ./configure --with-incompatible-bdb
RUN make

EXPOSE 9333
VOLUME /root/.litecoin

ADD litecoin.conf /root/.litecoin/litecoin.conf
CMD ./src/litecoind -debug
