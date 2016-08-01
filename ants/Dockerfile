FROM neurodebian:latest

ARG DEBIAN_FRONTEND=noninteractive

# Update packages and install the minimal set of tools
RUN apt-get -y update && \
    apt-get install -y curl bzip2

# Install ANTs
RUN mkdir -p /opt/ants && \
    curl -sSL "https://2a353b13e8d2d9ac21ce543b7064482f771ce658.googledrive.com/host/0BxI12kyv2olZVFhUcGVpYWF3R3c/ANTs-Linux_Ubuntu14.04.tar.bz2" \
    | tar -xjC /opt/ants --strip-components 1
ENV ANTSPATH /opt/ants
ENV PATH $ANTSPATH:$PATH

