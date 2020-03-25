FROM continuumio/miniconda3:4.8.2

LABEL maintainer="Luigi Di Fraia"

RUN conda config --add channels conda-forge

RUN conda update --quiet --yes conda
RUN conda install --quiet --yes python=3.6

RUN conda install --quiet --yes \
    python-blosc==1.8.3 \
    cytoolz==0.10.1 \
    dask==2.12.0 \
    nomkl==3.0 \
    numpy==1.18.1 \
    pandas==1.0.3 \
    tini==0.18.0 \
    && conda clean -tipsy \
    && find /opt/conda/ -type f,l -name '*.a' -delete \
    && find /opt/conda/ -type f,l -name '*.pyc' -delete \
    && find /opt/conda/ -type f,l -name '*.js.map' -delete \
    && find /opt/conda/lib/python*/site-packages/bokeh/server/static -type f,l -name '*.js' -not -name '*.min.js' -delete \
    && rm -rf /opt/conda/pkgs

COPY prepare.sh /usr/bin/prepare.sh

RUN mkdir /opt/app

ENTRYPOINT ["tini", "-g", "--", "/usr/bin/prepare.sh"]
