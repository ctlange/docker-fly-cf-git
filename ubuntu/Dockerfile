FROM ubuntu:16.04

MAINTAINER Romain Guichard <rgu@osones.io>

RUN apt update && apt install -yf ca-certificates

ADD https://ci.rguichard.fr/api/v1/cli?arch=amd64&platform=linux /usr/bin/fly
RUN chmod +x /usr/bin/fly
