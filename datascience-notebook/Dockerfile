FROM nielsbohr/python-notebook:latest
LABEL MAINTAINER="Rasmus Munk <rasmus.munk@nbi.ku.dk>"

USER root

# For opencv2 and basemap geos
RUN apt-get update \
    && apt-get install -yq --no-install-recommends \
    libx11-6 \
    libsm6 \
    libxext6 \
    libgeos-dev \
    libglib2.0-0 \
    libxrender1 \
    libgl1-mesa-glx \
    graphviz \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Run container as
USER $NB_USER

# Packages env
ENV BH_CONFIG=$PYTHON2_PATH/lib/python2.7/site-packages/bohrium_api/config.ini

# Install packages for python2/3 envs
RUN $PYTHON2_PATH/bin/pip install \
    numpy \
    bohrium \
    cython \
    opencv-python \
    six \
    nose \
    scipy \
    sympy \
    h5py \
    pandas \
    sklearn \
    seaborn \
    scikit-image \
    pillow \
    mlxtend \
    tqdm \
    pomegranate==0.10.0 \
    bokeh \
    Bottleneck \
    dask \
    datashader \
    nbconvert \
    netCDF4 \
    numba \
    statsmodels \
    xarray \
    graphviz \
    pystan \
    pymc3 \
    pyproj==1.9.6 \
    && $PYTHON3_PATH/bin/pip install \
    numpy \
    bohrium \
    cython \
    pandas \
    opencv-python \
    six \
    nose \
    sympy \
    scipy \
    h5py \
    sklearn \
    seaborn \
    scikit-image \
    pillow \
    mlxtend \
    tqdm \
    ruptures \
    pomegranate==0.10.0 \
    PyQt5 \
    bokeh \
    Bottleneck \
    dask \
    datashader \
    nbconvert \
    netCDF4 \
    numba \
    statsmodels \
    xarray \
    graphviz \
    pystan \
    pymc3 \
    pyproj==1.9.6 \
    && fix-permissions $CONDA_DIR

# Matplotlib basemap
RUN $PYTHON2_PATH/bin/pip install git+https://github.com/matplotlib/basemap.git \
    && $PYTHON3_PATH/bin/pip install git+https://github.com/matplotlib/basemap.git
