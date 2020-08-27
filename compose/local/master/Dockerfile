FROM continuumio/miniconda3:4.8.2
# FROM continuumio/miniconda3:4.8.2-alpine

ADD ./config/local/master /config/

RUN conda init bash

RUN conda env create -f /config/env/py3.6.10-ai-base.yml nomkl && \
    conda clean --all -f -y
