# Based on documentation from geteventstore.com
#Reference: http://docs.geteventstore.com/server/3.2.0/installing-from-debian-repositories/

FROM debian:jessie

ENV ES_VERSION v3.2.1

RUN apt-get -qq update
RUN apt-get install -qqy curl
RUN apt-get install -qqy apt-transport-https

RUN curl https://apt-oss.geteventstore.com/eventstore.key | apt-key add -

# pin in to ES_VERSION
RUN echo "deb [arch=amd64] https://apt-oss.geteventstore.com/ubuntu/ trusty $ES_VERSION" > /etc/apt/sources.list.d/eventstore.list
RUN apt-get -qq update
RUN apt-get -qqy install eventstore-oss
