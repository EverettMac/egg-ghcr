FROM        --platform=$TARGETOS/$TARGETARCH eclipse-temurin:21-jdk-jammy

LABEL       author="Embotic.XYZ" maintainer="luke@embotic.xyz"

LABEL       org.opencontainers.image.source="https://github.com/embotic-xyz/egg-ghcr"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apt update -y \
            && apt install -y \
                curl \
                lsof \
                ca-certificates \
                openssl \
                git \
                tar \
                sqlite3 \
                fontconfig \
                tzdata \
                iproute2 \
                libfreetype6 \
                tini \
				zip \
				unzip \
            && rm -f /usr/bin/dd \
            && rm -f /usr/bin/fallocate \
            && rm -f /usr/bin/truncate \
            && rm -f /usr/bin/xfs_mkfile \
            && useradd -d /home/container -m container
            

## Setup user and working directory
RUN         useradd -m -d /home/container -s /bin/bash container
USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

STOPSIGNAL SIGINT

COPY        --chown=container:container ./../entrypoint.sh /entrypoint.sh
RUN         chmod +x /entrypoint.sh
ENTRYPOINT    ["/usr/bin/tini", "-g", "--"]
CMD         ["/entrypoint.sh"]