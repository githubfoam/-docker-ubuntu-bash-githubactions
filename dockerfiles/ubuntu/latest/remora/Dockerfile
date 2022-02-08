FROM ubuntu:latest
LABEL org.opencontainers.image.authors="githubfoam"


RUN set -ex && apt-get update -qy && \
    apt-get dist-upgrade -yq && \
    apt-get purge unattended-upgrades && \
    apt-get clean all
    
RUN set -ex && apt-get update -yq  && apt-get install git -y && \
    git clone https://github.com/TACC/remora.git && cd remo** && \
    ./install.sh


#CMD ["remora"]