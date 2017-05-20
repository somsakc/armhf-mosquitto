FROM armhf/debian:jessie
MAINTAINER Somsak Chartsrisak <somsakc@hotmail.com>

LABEL Description="Eclipse Mosquitto MQTT Broker"

RUN apt-get update
RUN apt-get -y install mosquitto
RUN mkdir -p /mosquitto/config /mosquitto/data /mosquitto/log && \
    cp /etc/mosquitto/mosquitto.conf /mosquitto/config

COPY docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]
