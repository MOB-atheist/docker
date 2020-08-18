FROM ubuntu

RUN apt-get update
# ABSTRACTION OF APT INSTALLED PACKAGES
RUN apt-get install -y software-properties-common
# #D COMPUTER GRAPHICS LIBRARY
RUN apt-get install -y mesa-utils

#GNU BINARY UTILITIES
RUN apt-get install -y binutils

# REQUIREMENTS FOR STEAM
RUN dpkg --add-architecture i386
RUN add-apt-repository multiverse
RUN apt-get update

#KERNEL HEADERS
RUN apt-get -y update
RUN apt-get -y install linux-headers-$(uname -r)
# STEAM INSTALATION
RUN apt-get -y install -y steam

# FOR CUDA DRIVER BUILD
RUN apt-get -y install build-essential dkms
RUN apt-get install -y freeglut3 freeglut3-dev libxi-dev libxmu-dev
# WGET
RUN apt-get install -y wget

# CUDA DRIVER
RUN wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
RUN mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
RUN apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/7fa2af80.pub
RUN add-apt-repository "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/ /"
RUN apt-get update -y
RUN apt-get -y install cuda

RUN steam