# syntax=docker/dockerfile:1
FROM bench-common

ARG USERSPACE=false

RUN apt install -y iptables wireguard && \
    cargo install boringtun-cli

ADD entrypoint.sh \
    /bench/

WORKDIR /bench/

ENV WG_QUICK_USERSPACE_IMPLEMENTATION=boringtun \
    USERSPACE=$USERSPACE
ENTRYPOINT ./entrypoint.sh
