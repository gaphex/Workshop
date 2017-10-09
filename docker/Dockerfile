FROM tensorflow/tensorflow:1.3.0-gpu
MAINTAINER Denis Antyukhov gaphex@gmail.com

RUN apt-get update

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    curl \
    pkg-config \
    python3 \
    python3-dev \
    rsync \
    software-properties-common \
    unzip \
    sox \
    wget \
    git \
    htop \
    nano && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

RUN curl -O https://bootstrap.pypa.io/get-pip.py && python3 get-pip.py && rm get-pip.py
RUN pip --no-cache-dir install \
    Pillow \
    h5py \
    ipykernel \
    jupyter \
    keras \
    matplotlib \
    numpy \
    pandas \
    scipy \
    nltk \
    tqdm \
    seaborn \
    gensim \
    sklearn \
    tensorflow-gpu && \
    python3 -m ipykernel.kernelspec

RUN mkdir /root/Projects
WORKDIR /root/Projects
ENTRYPOINT jupyter notebook --port 7777 --allow-root
