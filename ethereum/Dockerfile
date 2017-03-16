FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install -qy build-essential
RUN apt-get install -qy git libgmp3-dev wget
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN wget https://storage.googleapis.com/golang/go1.8.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go1.8.linux-amd64.tar.gz

RUN mkdir -p /root/go
ENV PATH $PATH:/usr/local/go/bin
ENV GOPATH /root/go

RUN git clone https://github.com/ethereum/go-ethereum
WORKDIR go-ethereum

RUN make geth

EXPOSE 30303
VOLUME /root/.ethereum

CMD ./build/bin/geth --fast --verbosity=5 2>&1 | tee /root/.ethereum/debug.log
