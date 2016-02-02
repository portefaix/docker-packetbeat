# VERSION 1.0.0
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    portefaix/packetbeat

FROM portefaix/base:3.2
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

ENV PACKETBEAT_VERSION=1.0.0
ENV GOPATH /go

RUN apk add --update build-base go git mercurial bzr linux-grsec-dev libpcap libpcap-dev

RUN mkdir -p /go/src/github.com/elastic && \
    cd /go/src/github.com/elastic && \
    git clone https://github.com/elastic/beats.git -b ${PACKETBEAT_VERSION}
    # cd beats/packetbeat && \
    # make && \
    # mkdir -p /usr/share/packetbeat/bin/ && \
    # cp -r -a /go/src/github.com/packetbeat/* /usr/share/packetbeat && \
    # go clean -i -r && \
    # apk del --purge build-base go git mercurial && \
    # rm -rf /go /tmp/* /var/cache/apk/* /root/.n*

# ADD ./packetbeat.yml /usr/share/packetbeat/packetbeat.yml

# CMD ["/usr/share/packetbeat/packetbeat", "-e", "-c=/usr/share/packetbeat/packetbeat.yml"]
