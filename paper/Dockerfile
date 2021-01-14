FROM openjdk:11-jre

WORKDIR /data

RUN apt-get update && apt-get install -y \
    jq

# defaults, change in docker-compose.yml
ENV JVM_ARGS="-Xmx8G" \
    PAPER_ARGS="--nogui" \
    MC_RELEASE="1.16.4" \
    PAPER_BUILD="latest" \
    USER="1000" \
    GROUP="1000"

COPY start updater /
RUN chmod +x /start /updater

ENTRYPOINT /updater
EXPOSE 25565