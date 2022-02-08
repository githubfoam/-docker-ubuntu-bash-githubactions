FROM ubuntu:latest
LABEL org.opencontainers.image.authors="githubfoam"


RUN apt-get update -qy && \
    apt-get dist-upgrade -yq && \
    apt-get purge unattended-upgrades && \
    apt-get clean all

RUN set -ex && apt-get install sshfs -y && sshfs -V