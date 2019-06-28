FROM luigidifraia/dask:v1.1.0-alpha

RUN conda install --quiet --yes \
    -c conda-forge \
    boto3=1.9.179 \
    datacube=1.7 \
    descartes=1.1.0 \
    distributed=2.0.1 \
    folium=0.9.1 \
    geopandas=0.5.0 \
    hdmedians=0.13 \
    ipyleaflet=0.10.8 \
    matplotlib=3.1.0 \
    rasterstats=0.13.1 \
    ruamel=1.0 \
    ruamel.yaml=0.15.96 \
    scikit-image=0.15.0 \
    scikit-learn=0.21.2 \
    scipy=1.3.0 \
    seaborn=0.9.0 \
    shapely=1.6.4 \
    && conda clean -tipsy \
    && find /opt/conda/ -type f,l -name '*.a' -delete \
    && find /opt/conda/ -type f,l -name '*.pyc' -delete \
    && find /opt/conda/ -type f,l -name '*.js.map' -delete \
    && find /opt/conda/lib/python*/site-packages/bokeh/server/static -type f,l -name '*.js' -not -name '*.min.js' -delete \
    && rm -rf /opt/conda/pkgs
