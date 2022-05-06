FROM gcr.io/gae-runtimes/go116:go116_20211025_1_16_8_RC00

ARG UID=1000
ARG USER=intec

RUN apt update && \
    apt install -y sudo nano grc autoconf gcc make && \
    apt clean && \
    rm -rf /tmp/* && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -G www-data -u ${UID} -d /home/${USER} ${USER} && \
    chown -R ${USER}:${USER} /srv && \
    chown -R ${USER}:${USER} /var/log && \
    echo "${USER}  ALL = ( ALL ) NOPASSWD: ALL" >> /etc/sudoers

USER ${USER}
WORKDIR /srv/

# Set a runtime name (required by the base image)
ENV GAE_RUNTIME go116
