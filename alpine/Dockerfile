FROM alpine:3.7

MAINTAINER Romain Guichard <rgu@osones.io>

RUN apk add --update ca-certificates

ADD https://ci.rguichard.fr/api/v1/cli?arch=amd64&platform=linux /usr/bin/fly
RUN chmod +x /usr/bin/fly
