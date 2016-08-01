FROM neurodebian:latest

ARG DEBIAN_FRONTEND=noninteractive
# Update packages and install the minimal set of tools
RUN apt-get -y update && \
    apt-get install -y curl bzip2

# Install miniconda
RUN curl -sSLO https://repo.continuum.io/miniconda/Miniconda-latest-Linux-x86_64.sh && \
    /bin/bash Miniconda-latest-Linux-x86_64.sh -b -p /usr/local/miniconda && \
    rm Miniconda-latest-Linux-x86_64.sh

ENV PATH /usr/local/miniconda/bin:$PATH

# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8

# Add conda-forge channel in conda
RUN conda config --add channels conda-forge && \
    conda install -y nipype



# Install ANTs
RUN mkdir -p /opt/ants && \
    curl -sSL "https://2a353b13e8d2d9ac21ce543b7064482f771ce658.googledrive.com/host/0BxI12kyv2olZVFhUcGVpYWF3R3c/ANTs-Linux_Ubuntu14.04.tar.bz2" \
    | tar -xjC /opt/ants --strip-components 1
ENV ANTSPATH /opt/ants
ENV PATH $ANTSPATH:$PATH

