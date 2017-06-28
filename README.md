2017-06-28

SIMPLE MANUAL WAY TO TAKE EXECUTABLE SHOTDETECT
DOCKER ubuntu:17.04

docker run -it ubuntu:17.04

INSIDE DOCKER CONTAINER:

#DEPENDENCIES
apt-get update
apt-get install git

apt-get install cmake gcc g++
apt-get install -y libavformat-dev libavcodec-dev libavdevice-dev libavutil-dev libswscale-dev libavresample-dev libwxgtk3.0-dev 
apt-get install libgd2-xpm-dev
apt-get install libxml2-dev libxslt1-dev
apt-get install clang

#COMPILE
git clone https://github.com/bkz7abc/Shotdetect.git
cd Shotdetect
./compile.sh

# If you need executable file, take in /Shotdetect/build/shotdetect-cmd" 
# Shotdetect version "2.1.0-git719aa464976", Copyright (c) 2007-2013 Johan Mathe


ORIGINAL READ ME:

![Build status](https://api.travis-ci.org/johmathe/Shotdetect.svg?branch=master)

Shotdetect is a free software (LGPL) which detects shots and scenes from a video.
The result produced is a simple XML file containing all the informations about the movie generated.

# Install

## Dependencies
//sudo apt-get install libavdevice-dev libavformat-dev libgd2-noxpm libgd2-noxpm-dev
## Graphical version
//sudo apt-get install libwxgtk2.6-dev wx2.6-doc libwxgtk2.6-headers

## Building
mkdir -p build
cd  build
cmake ..

## Build command line version
mkdir -p build
cd build
cmake -D USE_WXWIDGETS:BOOL=OFF ..

# Example

## Shell

shotdetect -i myvideo.avi -o output_dir -s 60 -w -v -f -l -m -r

## Options details
-s : set threshold
The threshold is the level for shot detection. High will not detect a lot, low will detect a lot of false shots. A good choice is about 60.

-w : generates audio xml information
See the generated file for more details

-v : generates video xml informations
See the generated file for more details

-f : generates the first image of shots
-l : generates the last image of shots
-m : generates the thumbnails images
-r : generates the real size images

# Comments
johan.mathe@gmail.com