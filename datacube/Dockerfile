FROM luigidifraia/dask:v2.9.2-alpha

LABEL maintainer="Luigi Di Fraia"

RUN conda install --quiet --yes \
    -c conda-forge \
    boto3=1.11.4 \
    datacube=1.7 \
    descartes=1.1.0 \
    geopandas=0.6.2 \
    hdmedians=0.13 \
    ipyleaflet=0.12.0 \
    matplotlib=3.1.2 \
    rasterstats=0.14.0 \
    ruamel=1.0 \
    ruamel.yaml=0.16.5 \
    scikit-image=0.16.2 \
    scikit-learn=0.22.1 \
    scipy=1.4.1 \
    seaborn=0.9.0 \
    shapely=1.6.4 \
    && conda clean -tipsy \
    && find /opt/conda/ -type f,l -name '*.a' -delete \
    && find /opt/conda/ -type f,l -name '*.pyc' -delete \
    && find /opt/conda/ -type f,l -name '*.js.map' -delete \
    && find /opt/conda/lib/python*/site-packages/bokeh/server/static -type f,l -name '*.js' -not -name '*.min.js' -delete \
    && rm -rf /opt/conda/pkgs
