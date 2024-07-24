FROM        ghcr.io/embotic-xyz/egg-ghcr:debian

LABEL       author="Embotic.XYZ" maintainer="luke@embotic.xyz"

LABEL       org.opencontainers.image.source="https://github.com/embotic-xyz/egg-ghcr"
LABEL       org.opencontainers.image.licenses=MIT

RUN			dpkg --add-architecture i386 \
			&& apt update && apt upgrade -y \
			&& apt install -y lib32gcc-s1 lib32stdc++6 libstdc++5:i386


