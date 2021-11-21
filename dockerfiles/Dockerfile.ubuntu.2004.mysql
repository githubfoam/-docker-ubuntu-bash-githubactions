# https://hub.docker.com/_/ubuntu
FROM ubuntu:20.04
LABEL org.opencontainers.image.authors="githubfoam"

WORKDIR /tmp

RUN apt-get update -qy && \ 
    apt-get dist-upgrade -yq && \
    apt-get purge unattended-upgrades && \
    apt-get clean all

RUN apt-get update \
    && apt-get install -y --no-install-recommends mysql-client \
    && rm -rf /var/lib/apt/lists/

ENTRYPOINT ["mysql"]
