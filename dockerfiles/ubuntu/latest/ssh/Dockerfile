FROM ubuntu:latest
LABEL org.opencontainers.image.authors="githubfoam"


RUN set -ex && apt-get update -qy && \
    apt-get dist-upgrade -yq && \
    apt-get purge unattended-upgrades && \
    apt-get clean all
    
RUN set -ex && apt-get update -yq && apt-get install openssh-server -y && \
    ssh -V && \
    echo 'root:mypassword' | chpasswd && \
    sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

    EXPOSE 22

    CMD ["/usr/sbin/sshd", "-D"]