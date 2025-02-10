# Barrier Debian Package Fix

This repository contains a fixed version of Barrier 2.4.0 for Debian Trixie.
You can find the original Barrier at: https://github.com/debauchee/barrier

## What’s Fixed?
- **Build error:** `std::uint8_t` not recognized 

## Installation
Download and install the `.deb` package:
```sh
wget https://github.com/cpendlebury/barrier-trixie/releases/latest/download/barrier-2.4.0-trixie.deb
sudo dpkg -i barrier-2.4.0-trixie.deb

## Build from source
```sh
sudo apt update && sudo apt install -y \
    cmake g++ git libavahi-compat-libdnssd-dev \
    libcurl4-openssl-dev libssl-dev \
    qtbase5-dev qttools5-dev qttools5-dev-tools \
    libx11-dev libxi-dev libxtst-dev \
    make xorg-dev
cd src/barrier
mkdir build && cd build
cmake .. -DCMAKE_CXX_STANDARD=17
make -j$(nproc)
sudo make install

