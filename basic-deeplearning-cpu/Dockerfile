FROM ubuntu:xenial

MAINTAINER Dmitrii Budylskii "budmitr@gmail.com"

# Configure environment
ENV CONDA_DIR /opt/miniconda
ENV USER dockeruser
ENV USERGROUP 1000
ENV HOME /home/$USER

# Basic setups
EXPOSE 8888
RUN apt-get -y update && \
    apt-get install -y wget python-pip python-dev

# Create local user
RUN useradd -m -s /bin/bash -N -u $USERGROUP $USER

# Install conda
RUN wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh -q -O /tmp/miniconda.sh && \
    bash /tmp/miniconda.sh -b -p $CONDA_DIR && \
    rm /tmp/miniconda.sh && \
    chown $USER $CONDA_DIR -R

# Switch to local user
USER $USER
ENV PATH $CONDA_DIR/bin:$PATH
WORKDIR $HOME

# prepare default python 2.7 environment
RUN pip install --upgrade pip && \
    pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.11.0-cp27-none-linux_x86_64.whl && \
    pip install h5py jupyter keras matplotlib pandas   
