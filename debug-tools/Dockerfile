FROM debian:10
MAINTAINER Lee Verberne <lee@blarg.org>

RUN apt-get update && apt-get install -y \
        lsof \
        netcat-openbsd \
        procps \
        strace \
        tmux \
        traceroute \
    && rm -rf /var/lib/apt/lists/*
