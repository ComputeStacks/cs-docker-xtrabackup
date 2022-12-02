FROM ghcr.io/computestacks/cs-docker-base:ubuntu-focal

LABEL maintainer="ComputeStacks <hello@computestacks.com>"

RUN wget https://repo.percona.com/apt/percona-release_latest.$(lsb_release -sc)_all.deb \
    && dpkg -i percona-release_latest.$(lsb_release -sc)_all.deb

RUN set -ex; \
    \
    apt-get update; \
    apt-get install -y \
            percona-xtrabackup-24 \
            mysql-client \
    ; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*;
