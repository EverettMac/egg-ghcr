FROM        --platform=$TARGETOS/$TARGETARCH adoptopenjdk/openjdk11:alpine-jre

LABEL       author="Embotic.XYZ" maintainer="luke@embotic.xyz"

LABEL       org.opencontainers.image.source="https://github.com/embotic-xyz/egg-ghcr"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache python3 py3-tz ca-certificates curl fontconfig git openssl sqlite tar tzdata \
			    && adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]
