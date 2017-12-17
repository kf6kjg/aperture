# InWorldz aperture texture and mesh server

Aperture is a simple not quite compliant HTTP/1.1 server that sends texture and
mesh data to viewer software connected to the InWorldz grid

## Build requirements

- [CMake 3.8.2 or later](https://cmake.org/)
- [Conan 0.28.1 or later](https://www.conan.io/)

You will need to add the SlideWave LLC and the conan-community repositories to obtain prebuilt packages:

```dos
conan remote add slidewave https://api.bintray.com/conan/slidewavellc/conan-libs
conan remote add conan-community https://api.bintray.com/conan/conan-community/conan
```

## Sample cmake build command for Windows 64-bit

```dos
conan install . -s build_type=Debug -s arch=x86_64 -s compiler.runtime=MTd --build=missing
mkdir build && cd build
cmake -G "Visual Studio 15 2017 Win64" .. -DCMAKE_BUILD_TYPE=Debug
```

## Directions for Ubuntu 16.04 LTS

These are the basic commands in order based off of my terminal history, they may not be precise.

1. Install cmake, protobuf-compiler, libboost1.58-all-dev
1. clone aperture
1. cd aperture
1. mkdir build
1. cd build
1. cmake ..
1. make
1. Create the configuration file

A bare-bones aperture.cfg file is:

```ini
http_listen_port = <port number>
caps_token = 2960079
whip_url = whip://<password>@<ip>:32700
```
