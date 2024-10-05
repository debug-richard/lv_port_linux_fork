ARG BASE_OS
FROM "BASE_OS"

RUN DEBIAN_FRONTEND="noninteractive" apt-get update

RUN DEBIAN_FRONTEND="noninteractive" apt-get install -y tzdata ca-certificates
RUN ln -fs /usr/share/zoneinfo/Europe/Berlin /etc/localtime && dpkg-reconfigure -f noninteractive tzdata

# Build tools
RUN DEBIAN_FRONTEND="noninteractive" apt-get install -y make cmake build-essential

# Required for LV_USE_SDL
RUN DEBIAN_FRONTEND="noninteractive" apt-get install -y libsdl2-dev libsdl2-image-dev 

# Required for LV_USE_LINUX_DRM. linux-headers-amd64 provides an included header file.
RUN DEBIAN_FRONTEND="noninteractive" apt-get install -y libdrm-dev linux-headers-amd64

RUN mkdir /workdir
WORKDIR /workdir
# RUN ls -la
# RUN mkdir build/ && cd build/ && cmake .. && make -j
