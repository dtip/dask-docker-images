FROM continuumio/miniconda3:4.5.4

LABEL maintainer="Luigi Di Fraia"

RUN conda install --quiet --yes \
    -c conda-forge \
    python-blosc==1.8.1 \
    cytoolz==0.10.1 \
    dask==2.9.2 \
    lz4==3.0.2 \
    nomkl==3.0 \
    numpy==1.17.3 \
    pandas==0.25.2 \
    python==3.6.7 \
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
