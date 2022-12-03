FROM ghcr.io/computestacks/cs-docker-base:ubuntu-focal

LABEL maintainer="ComputeStacks <hello@computestacks.com>"
LABEL org.opencontainers.image.authors="https://computestacks.com"
LABEL org.opencontainers.image.source="https://github.com/ComputeStacks/cs-docker-xtrabackup/tree/main/2.4"
LABEL org.opencontainers.image.url="https://github.com/ComputeStacks/cs-docker-xtrabackup/tree/main/2.4"
LABEL org.opencontainers.image.title="Percona xtrabackup 2.4"

RUN wget https://repo.percona.com/apt/percona-release_latest.$(lsb_release -sc)_all.deb \
    && dpkg -i percona-release_latest.$(lsb_release -sc)_all.deb \
    && percona-release enable-only tools

RUN set -ex; \
    \
    apt-get update; \
    apt-get install -y \
            percona-xtrabackup-24 \
            mysql-client \
    ; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*;
