FROM itzg/minecraft-server:java21-alpine

ENV EULA=TRUE
ENV NETWORK_COMPRESSION_THRESHOLD=-1
ENV MAX_PLAYERS=100

ENV ALLOW_FLIGHT=TRUE
ENV PVP=FALSE
ENV DIFFICULTY=peaceful
ENV ALLOW_NETHER=FALSE
ENV ANNOUNCE_PLAYER_ACHIEVEMENTS=FALSE
ENV SPAWN_ANIMALS=FALSE
ENV SPAWN_MONSTERS=FALSE
ENV SPAWN_NPCS=FALSE
ENV VIEW_DISTANCE=6

ENV PLUGINS_FILE=/extras/plugins.txt
COPY plugins.txt /extras/plugins.txt

COPY --chmod=755 scripts/* /usr/bin/
RUN mkdir /cached_plugins
RUN /usr/bin/download_plugins_from_ci https://ci.viaversion.com/ ViaVersion ViaVersion
RUN /usr/bin/download_plugins_from_ci https://ci.viaversion.com/ ViaBackwards ViaBackwards
RUN /usr/bin/download_plugins_from_ci https://ci.lucko.me/ LuckPerms LuckPerms-Bukkit
RUN /usr/bin/download_plugins_from_ci https://ci.dmulloy2.net/ ProtocolLib ProtocolLib