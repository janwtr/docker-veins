#!/usr/bin/env docker build --build-arg VERSION=1.2.0 -t janwtr/omnetpp-gui-sumo:lates .
#

FROM janwtr/omnetpp-gui:latest as base
LABEL maintainer="jan@ums.ac.id"

RUN apt-get update -y && \
	apt-get install -y --no-install-recommends \			
	cmake python g++ libxerces-c-dev libfox-1.6-dev libgdal-dev libproj-dev libgl2ps-dev swig

ARG VERSION=1.2.0

WORKDIR /root

# Download and extract source code
RUN wget http://downloads.sourceforge.net/project/sumo/sumo/version%20$VERSION/sumo-src-$VERSION.tar.gz

RUN tar xzf sumo-src-$VERSION.tar.gz && \
    rm sumo-src-$VERSION.tar.gz

# Configure and build from source.
RUN cd /root/sumo-$VERSION && \
	export SUMO_HOME="\root\sumo-$VERSION" && \
	mkdir sumo/build/cmake-build && \
	cd sumo/build/cmake-build && \
	cmake ../.. && \
	make -j$(nproc)
