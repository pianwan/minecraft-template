FROM itzg/minecraft-server

ENV EULA=TRUE
ENV NETWORK_COMPRESSION_THRESHOLD=-1
ENV MAX_PLAYERS=100

ENV ALLOW_FLIGHT=TRUE
ENV DIFFICULTY=hard
ENV VIEW_DISTANCE=8

ENV PLUGINS_FILE=/extras/plugins.txt
COPY plugins.txt /extras/plugins.txt

COPY --chmod=755 scripts/* /usr/bin/
RUN mkdir /cached_plugins
RUN /usr/bin/download_plugins_from_ci https://ci.viaversion.com/ ViaVersion ViaVersion
RUN /usr/bin/download_plugins_from_ci https://ci.viaversion.com/ ViaBackwards ViaBackwards
RUN /usr/bin/download_plugins_from_ci https://ci.lucko.me/ LuckPerms LuckPerms-Bukkit
RUN /usr/bin/download_plugins_from_ci https://ci.dmulloy2.net/ ProtocolLib ProtocolLib
RUN /usr/bin/download_plugins_from_ci https://ci.athion.net/ FastAsyncWorldEdit FastAsyncWorldEdit-Paper
RUN /usr/bin/download_plugins_from_ci https://ci.codemc.io/view/Author/job/pop4959 Chunky Chunky-Bukkit
RUN /usr/bin/download_plugins_from_ci https://ci.codemc.io/view/Author/job/pop4959 ChunkyBorder ChunkyBorder-Bukkit