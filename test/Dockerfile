FROM debian:latest

RUN apt-get update
RUN apt-get install -y openssh-server

WORKDIR /root

COPY setup .

ENV USERNAME test_user
ENV HOST_PUBKEY ssh-rsa TESTPUBKEY

RUN ./setup
