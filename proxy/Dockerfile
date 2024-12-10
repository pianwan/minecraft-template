FROM itzg/mc-proxy

RUN apt-get update && apt-get install -y jq && apt-get clean

WORKDIR /server

COPY --chmod=755 scripts/* /usr/bin/
RUN mkdir /cached_plugins
RUN /usr/bin/download_plugins_from_ci https://ci.viaversion.com/ ViaVersion ViaVersion
RUN /usr/bin/download_plugins_from_ci https://ci.lucko.me/ LuckPerms LuckPerms-Velocity