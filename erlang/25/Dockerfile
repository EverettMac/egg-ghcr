FROM        --platform=$TARGETOS/$TARGETARCH erlang:25-alpine

LABEL       author="Embotic.XYZ" maintainer="luke@embotic.xyz"

LABEL       org.opencontainers.image.source="https://github.com/embotic-xyz/egg-ghcr"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache ca-certificates curl git openssl sqlite tar tzdata iproute2 \
				&& adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]
