FROM ubuntu:latest
LABEL org.opencontainers.image.authors="githubfoam"


RUN set -ex && apt-get update -qy && \
    apt-get dist-upgrade -yq && \
    apt-get purge unattended-upgrades && \
    apt-get clean all

#Zram is a compressed RAM-based swap device designed for systems with no physical swap partitions    
RUN set -ex && apt-get update -yq  && apt-get install zram-config -y && \
    systemctl start zram-config


#CMD ["remora"]