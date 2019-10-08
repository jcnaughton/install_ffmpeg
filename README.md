# install_ffmpeg

#!/bin/sh

sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install git -y
sudo apt-get -y install autoconf automake build-essential libass-dev libfreetype6-dev \
libsdl2-dev libtheora-dev libtool libva-dev libvdpau-dev libvorbis-dev libxcb1-dev libxcb-shm0-dev \
libxcb-xfixes0-dev pkg-config texinfo zlib1g-dev \
libsdl2-dev libva-dev libvdpau-dev libxcb1-dev libxcb-shm0-dev libxcb-xfixes0-dev \
yasm libx264-dev libfdk-aac-dev libmp3lame-dev libvpx-dev \
gnutls-bin libgnutls-dev
git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg
cd ffmpeg
./configure --enable-gpl --enable-libx264 --enable-libmp3lame --enable-libvpx --enable-gnutls
make
sudo make install

ffmpeg --help
