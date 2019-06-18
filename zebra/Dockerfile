FROM ubuntu:16.04

RUN apt-get update && apt-get install -qy git
RUN apt-get install -qy build-essential curl

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH "/root/.cargo/bin:${PATH}"

RUN apt-get install -qy cmake
RUN git clone https://github.com/ZcashFoundation/zebra
WORKDIR zebra
RUN cargo build -p zebra --release

VOLUME /root/zcash
VOLUME /root/.local/share/zebra/

CMD ./target/release/zebra
