# hash:sha256:1e81545bba2f1533da0a560fe7906626019885daf8e9441ca016fc1fb2cb4d95
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/jupyterlab:3.6.1-miniconda4.12.0-python3.9-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential=12.8ubuntu1.1 \
    && rm -rf /var/lib/apt/lists/*

RUN conda install -y \
        matplotlib==3.7.1 \
        numpy==1.25.2 \
        pip==23.2.1 \
        scikit-learn==1.3.0 \
        seaborn==0.12.2 \
        setuptools==65.6.3 \
    && conda clean -ya

RUN pip install -U --no-cache-dir \
    caveclient==5.25.2 \
    meshparty==1.16.14 \
    nglui==2.14.3 \
    standard-transform==1.4.0
