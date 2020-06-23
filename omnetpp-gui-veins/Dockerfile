#!/usr/bin/env docker build --build-arg VERSION=5.0 -t janwtr/omnetpp-gui-veins:lates .
#

FROM janwtr/omnetpp-gui-sumo:latest as base
LABEL maintainer="jan@ums.ac.id"

RUN apt-get update -y && \
	apt-get install -y --no-install-recommends \
	build-essential gcc g++ bison flex perl tcl-dev tk-dev blt libxml2-dev zlib1g-dev \
	default-jre doxygen graphviz libwebkitgtk-1.0-0 openmpi-bin libopenmpi-dev \
	libpcap-dev autoconf automake libtool libproj-dev libfox-1.6-dev \
	libgdal-dev libxerces-c-dev qt4-dev-tools

ARG VERSION=5.0

WORKDIR /root

ADD sumo-launchd.py .
ADD run-sumo.sh .
RUN chmod +x run-sumo.sh
