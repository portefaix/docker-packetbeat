# VERSION 1.0.0
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    portefaix/packetbeat

FROM portefaix/base:3.2
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

ENV PACKETBEAT_VERSION=1.0.0-beta2 \
	PACKETBEAT_ARCH=x86_64 \
	GOROOT=/usr/lib/go \
	GOPATH=/gopath \
	GOBIN=/gopath/bin \
	PATH=$PATH:$GOROOT/bin:$GOPATH/bin

RUN apk add --update wget curl ca-certificates
RUN apk add git mercurial bzr go
RUN apk del wget ca-certificates && \
    rm /var/cache/apk/*

# Install Packetbeat
RUN curl -Ls https://download.elastic.co/beats/packetbeat/packetbeat-$PACKETBEAT_VERSION-$PACKETBEAT_ARCH.tar.gz | tar -xz -C /usr/share
ADD ./packetbeat.yml /usr/share/packetbeat/packetbeat.yml

CMD ["/usr/share/packetbeat", "-e", "-c=/usr/share/packetbeat/packetbeat.yml"]

