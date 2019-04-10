FROM ubuntu:16.04

MAINTAINER Romain Guichard <rgu@osones.io>
ENV K8S_VERSION v1.10.0

RUN apt update && apt install -yf ca-certificates jq git

ADD https://ci.rguichard.fr/api/v1/cli?arch=amd64&platform=linux /usr/bin/fly
RUN chmod +x /usr/bin/fly

ADD https://github.com/concourse/concourse/releases/download/v3.14.1/fly_linux_amd64 /usr/bin/fly3
RUN chmod +x /usr/bin/fly3

# Install Cloud Foundry cli
ADD https://packages.cloudfoundry.org/stable?release=linux64-binary&source=github /tmp/cf-cli.tgz
RUN mkdir -p /usr/bin && \
  tar -xzf /tmp/cf-cli.tgz -C /usr/bin && \
  cf --version && \
  rm -f /tmp/cf-cli.tgz

ADD https://storage.googleapis.com/kubernetes-release/release/"$K8S_VERSION"/bin/linux/amd64/kubectl /usr/bin/kubectl
RUN chmod +x /usr/bin/kubectl
