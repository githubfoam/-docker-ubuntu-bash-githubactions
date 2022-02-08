FROM ubuntu:latest
LABEL org.opencontainers.image.authors="githubfoam"


RUN set -ex && apt-get update -qy && \
    apt-get dist-upgrade -yq && \
    apt-get purge unattended-upgrades && \
    apt-get clean all

#This modified kernel features the optimized CPU scheduler, Budget Fair Queueing (BFQ)
#I/O scheduler (the tool that controls the disk read/write requests management, 
#which plays a huge role in keeping the OS responsive when the disk is under heavy 
#load), and other tweaks for better preemptive multitasking and lower latencies. 
RUN set -ex && \
    echo 'deb http://deb.xanmod.org releases main' | \
    tee /etc/apt/sources.list.d/xanmod-kernel.list && \
    wget -qO - https://dl.xanmod.org/gpg.key |  apt-key add && \
    apt-get update -qy && apt-get install linux-xanmod -y

#CMD ["remora"]