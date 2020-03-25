FROM continuumio/miniconda3:4.8.2

LABEL maintainer="Luigi Di Fraia"

RUN conda config --add channels conda-forge

RUN conda update --yes conda
RUN conda install --yes python=3.6

RUN conda install --quiet --yes \
    boto3 \
    datacube \
    descartes \
    distributed \
    folium \
    geopandas \
    hdmedians \
    ipyleaflet \
    matplotlib \
    rasterstats \
    ruamel \
    ruamel.yaml \
    scikit-image \
    scikit-learn \
    scipy \
    seaborn \
    shapely \
    python-blosc \
    cytoolz \
    dask \
    nomkl \
    numpy \
    pandas \
    tini \
    && conda clean -tipsy \
    && find /opt/conda/ -type f,l -name '*.a' -delete \
    && find /opt/conda/ -type f,l -name '*.pyc' -delete \
    && find /opt/conda/ -type f,l -name '*.js.map' -delete \
    && find /opt/conda/lib/python*/site-packages/bokeh/server/static -type f,l -name '*.js' -not -name '*.min.js' -delete \
    && rm -rf /opt/conda/pkgs

COPY prepare.sh /usr/bin/prepare.sh

RUN mkdir /opt/app

ENTRYPOINT ["tini", "-g", "--", "/usr/bin/prepare.sh"]
