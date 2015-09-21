# Based on documentation from geteventstore.com
#Reference: http://docs.geteventstore.com/server/3.2.0/installing-from-debian-repositories/

FROM debian:jessie

ENV ES_VERSION v3.2.0
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -qq update \
    && apt-get install -qq apt-utils \
    && apt-get install -qq curl \
    && apt-get install -qq apt-transport-https

RUN curl -sS https://apt-oss.geteventstore.com/eventstore.key | apt-key add -

RUN echo "deb [arch=amd64] https://apt-oss.geteventstore.com/ubuntu/ trusty $ES_VERSION" > /etc/apt/sources.list.d/eventstore.list \
  && apt-get -qq update \
  && apt-get -qq install eventstore-oss

EXPOSE 2113
EXPOSE 1113

VOLUME /data/db
VOLUME /data/logs

# Eventstore configuration are found at /etc/eventstore/eventstore.conf

#ENTRYPOINT service eventstore start
