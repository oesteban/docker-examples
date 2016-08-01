FROM neurodebian:latest

ARG DEBIAN_FRONTEND=noninteractive
RUN sed -i -e 's,main$,main contrib non-free,g' /etc/apt/sources.list.d/neurodebian.sources.list && \
    apt-get -y update && \
    apt-get install -y fsl-core && \
    echo ". /etc/fsl/fsl.sh" >> /etc/bash.bashrc

ENV FSLDIR /usr/share/fsl/5.0
ENV PATH /usr/lib/fsl/5.0:$PATH
