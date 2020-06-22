#!/usr/bin/env docker build --build-arg VERSION=5.0 -t janwtr/omnetpp-gui-veins:lates .
#

FROM janwtr/omnetpp-gui-sumo:latest as base
MAINTAINER Jan W <jan@ums.ac.id>
RUN apt-get update -y && apt-get install -y --no-install-recommends \
	build-essential gcc g++ bison flex perl tcl-dev tk-dev blt libxml2-dev zlib1g-dev \
	default-jre doxygen graphviz libwebkitgtk-1.0-0 openmpi-bin libopenmpi-dev \
	libpcap-dev autoconf automake libtool libproj-dev libgdal1-dev libfox-1.6-dev \
	libgdal-dev libxerces-c-dev qt4-dev-tools


ARG VERSION=5.0

WORKDIR /root/models

RUN wget https://github.com/sommer/veins/archive/veins-$VERSION.tar.gz
RUN tar xzf -O veins veins-$VERSION.tar.gz && \
    rm veins-$VERSION.tar.gz