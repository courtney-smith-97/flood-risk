
# FROM ubuntu:20.04
FROM ubuntu:20.04

# LABEL about the custom image
LABEL maintainer="djortiz"
LABEL version="0.1"
LABEL description="This is custom Docker Image for w210 Flood Project"

# Install base utilities
RUN apt-get update && \
    apt-get install -y build-essential && \
    apt-get install -y wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install miniconda
ENV CONDA_DIR /opt/conda
RUN wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh && \
     /bin/bash ~/miniconda.sh -b -p /opt/conda
     
# Put conda in path so we can use conda activate
ENV PATH=$CONDA_DIR/bin:$PATH

# Install CMAKE for GEOS
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt-get -y install tzdata
RUN apt-get update && apt-get -y install cmake

# Install GEOS
RUN wget https://download.osgeo.org/geos/geos-3.11.0.tar.bz2 && \
    tar xvfj geos-3.11.0.tar.bz2
RUN cd geos-3.11.0 && \
     mkdir _build && \
     cd _build && \
     cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local .. && \
     make && \
     ctest && \
     make install

# Install Spatial Index
RUN conda install -c conda-forge libspatialindex=1.9.3


# Install required python packages for GeoPandas'
RUN pip3 install pillow pysal geopandas rtree geopy

# Install git
RUN apt-get install -y git

# Install jupyter
RUN pip3 install jupyter -U && pip3 install jupyterlab

# Install Rasterio
RUN apt-get install -y software-properties-common
RUN add-apt-repository ppa:ubuntugis/ppa && \
    apt-get update
RUN apt-get install -y python-numpy gdal-bin libgdal-dev
RUN pip install rasterio

# Install GDAL
#RUN conda install -c conda-forge gdal
#RUN pip3 install --global-option=build_ext --global-option="-I/usr/include/gdal" GDAL==`gdal-config --version`


#RUN pip install pip==18.1
RUN add-apt-repository ppa:ubuntugis/ppa && apt-get update && \
    apt-get update && \
    apt-get install -y gdal-bin && \
    apt-get install -y libgdal-dev && \
    apt-get install -y python3-dev && \
    export CPLUS_INCLUDE_PATH=/usr/include/gdal && \
    export C_INCLUDE_PATH=/usr/include/gdal && \
    pip install GDAL==`gdal-config --version`
    
# Install Earthpy
RUN pip install earthpy

# Install PySal
RUN pip install pysal

# Install Pysal ESDA
RUN pip install -U esda

# Install splot
RUN pip install splot

# Basemap
#RUN pip install pip==18.1
#RUN pip3 install https://github.com/matplotlib/basemap/archive/v1.0.7rel.tar.gz
    
RUN mkdir workspace

# Launch Jupyter Server
EXPOSE 8888
ENTRYPOINT ["jupyter", "lab","--ip=0.0.0.0","--allow-root"]
