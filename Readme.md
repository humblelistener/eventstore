# Event store docker container

## Allows injecting your own event store configuration

## Includes sample to deploy to elastic beanstalk single instance docker container

## Why another event store docker image?
The docker containers out there have configurations pretty much set in them. This container will allow you to inject a configuration file (eventstore.conf).

Refer to configuration section in [eventstore-docs](http://docs.geteventstore.com/server/3.2.0/installing-from-debian-repositories/).

## How to use?

There are two ways to use this

1. **using with Default configuration**

2. **using with custom configuration**


### Consuming with default configuration

``docker run -p 2113:2113 -p 1113:1113 kpadmanabhan/eventstore``

### Consuming with custom configuration

A sample configuration file can be found at [eventstore-docker-default-configuration](https://github.com/humblelistener/eventstore/blob/master/latest/eventstore.conf).

Documentation on what can go into eventstore configuration file can be found at [eventstore-arguments](http://docs.geteventstore.com/server/3.2.0/command-line-arguments/).

1. Create your own configuration file, using the above references.
2. Name it "eventstore.conf"
3. Create your own docker file with the following
```
FROM kpadmanabhan/eventstore
```
4. Ensure the dockerfile and evenstore.conf are in the same directory.

*Note: Port exposing is currently limited, it can only use 2113 & 1113.*


The image uses ONBUILD trigger to replace the configuration file.
[Refer to ONBUILD section here](https://docs.docker.com/reference/builder/).

### Deploying event store on aws elastic beanstalk
The repository contains a [sample folder](https://github.com/humblelistener/eventstore/tree/master/elastic-beanstalk-deploy-sample) that can be compressed and used to deploy on elastic beanstalk docker stack application environment.

This is provided only as an example to use the docker image and is recommended only to quickly setup a development environment or an environment to spike the event store. _It does not solve the clustering challenges in deploying event store in docker_.
