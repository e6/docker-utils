FROM ubuntu:12.04
MAINTAINER Syoyo Fujita(syoyo@lighttransport.com) -- ORIGINAL
MAINTAINER e6 -- for AMD

RUN apt-get update
RUN apt-get -y --force-yes install x-window-system
RUN apt-get install -y binutils
RUN apt-get install -y pkg-config
RUN apt-get install -y x11vnc
RUN apt-get install -y mesa-utils
RUN apt-get install -y libgtk2.0-0
RUN apt-get install -y twm
RUN apt-get install -y curl
RUN apt-get install -y unzip
# INSTALL FOR AMD DRIVERS TO INSTALL
# RUN apt-get install -y linux-headers-3.16.0-25-generic
#RUN apt-get install -y make
#RUN apt-get install -y gcc
#RUN apt-get install -y dh-modaliases
#RUN apt-get install -y execstack
#RUN apt-get install -y dpkg-dev
#RUN apt-get install -y debhelper
#RUN apt-get install -y dkms
#RUN apt-get install -y lib32gcc1

RUN echo 'export DISPLAY=:0' >> ~/.bashrc

# AMD --
# check for newest version http://support.amd.com/en-us/download/desktop?os=Linux+x86
RUN cd /tmp && curl --referer "http://support.amd.com/en-us/download/desktop?os=Linux+x86" -o amd-catalyst-14-9-linux-x86-x86-64.zip http://www2.ati.com/drivers/linux/amd-catalyst-14-9-linux-x86-x86-64.zip

#  https://help.ubuntu.com/community/BinaryDriverHowto/AMD
RUN ./amd-driver-installer-14.301.1001-x86.x86_64.run --buildpkg Ubuntu/precise

# FOR NVIDIA --
#ADD NVIDIA-DRIVER.run /tmp/NVIDIA-DRIVER.run
#RUN sh /tmp/NVIDIA-DRIVER.run -a -N --ui=none --no-kernel-module
#RUN nvidia-xconfig -a --use-display-device=None --enable-all-gpus --virtual=1280x1024
#RUN rm /tmp/NVIDIA-DRIVER.run
