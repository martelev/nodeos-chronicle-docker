FROM ubuntu:18.10

RUN apt update && \
    apt install -y wget && \
    wget https://github.com/eosio/eos/releases/download/v1.8.0-rc2/eosio_1.8.0-rc2-ubuntu-18.04_amd64.deb && \
    apt install -y ./eosio_1.8.0-rc2-ubuntu-18.04_amd64.deb && \
    mkdir /root/eos

COPY config.ini /root/.local/share/eosio/nodeos/config/config.ini
COPY genesis.json /root/eos/genesis.json

ENTRYPOINT exec /usr/bin/nodeos --disable-replay-opts --genesis-json=/root/eos/genesis.json