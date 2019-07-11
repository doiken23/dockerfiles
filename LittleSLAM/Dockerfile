FROM ubuntu:16.04

RUN apt-get update && apt-get install -y \
    git \
    wget \
    unzip \
    build-essential \
    cmake \
    libboost-all-dev \
    libeigen3-dev \
    gnuplot \
    gnuplot-x11 \
    libx11-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /root
RUN git clone --recursive https://github.com/furo-org/LittleSLAM.git
RUN mkdir /root/LittleSLAM/build

WORKDIR /root/LittleSLAM/build
RUN cmake ..
RUN make

WORKDIR /root/LittleSLAM/dataset
RUN wget https://furo.org/software/little_slam/dataset.zip
RUN unzip dataset.zip && rm dataset.zip

CMD ["bin/bash"]
