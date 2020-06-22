#!/usr/bin/env docker build --build-arg VERSION=1.2.0 -t janwtr/omnetpp-gui-sumo:lates .
#

FROM janwtr/omnetpp-gui:latest as base
MAINTAINER Jan W <jan@ums.ac.id>
RUN apt-get update -y && apt-get install -y --no-install-recommends qt5-default libqt5opengl5-dev \
            libgtk-3-0 libwebkitgtk-3.0-0 default-jre gcc g++ gdb libxml2-dev

# first stage - build OMNeT++ with GUI
FROM base as builder

ARG VERSION=1.2.0

WORKDIR /root

# Install system dependencies.
RUN apt-get update -y && apt-get -qq install -y\
    wget \
    g++ \
    make \
    libxerces-c-dev \
    libfox-1.6-0 libfox-1.6-dev \
    python2.7

# Download and extract source code
RUN wget http://downloads.sourceforge.net/project/sumo/sumo/version%20$VERSION/sumo-src-$VERSION.tar.gz
RUN tar xzf sumo-src-$VERSION.tar.gz && \
    rm sumo-src-VERSION.tar.gz

# Configure and build from source.
RUN cd \root\sumo-$VERSION && ./configure && make install
