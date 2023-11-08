# Havoc_windows
Compiled Havoc for windows operating system
# project:
**https://github.com/HavocFramework/Havoc**
# steps
Since the original project is working in linux and macos, before compiling the source code and CMakelists.txt need to make some modifications to ensure that windows can be pass, I have 
 uploaded to github, you can git clone and compile .
## 1. download source
git clone https://github.com/HavocFramework/Havoc
cd Havoc\client
git clone https://github.com/gabime/spdlog
## 2. install qt5 and python310
download and install qt5 and python
### install qt5
mirror list:https://download.qt.io/static/mirrorlist/
chose fast mirror address.
qt-unified-windows-x64-online.exe --mirror https://ftp.yz.yamagata-u.ac.jp/pub/qtproject/ 
### install python310
https://www.python.org/ftp/python/3.10.10/python-3.10.10-amd64.exe
## 3. install mingw
https://github.com/niXman/mingw-builds-binaries/releases
## 4. add env
set env for client compile
Qt5_DIR=E:\Qt\5.15.2\mingw81_64
PATH+= E:\Qt\Tools\CMake_64\bin;E:\Qt\Tools\mingw810_64\bin;e:\Tools\x86_64-w64- mingw32\13.2.0\bin
## 5.build teamserver
go build teamserver
cd teamserver
go env -w GO111MODULE="on"
go build -ldflags="-s -w" -o ..\havoc_server.exe main.go
## 6 .cmake-gui generate mingw makefiles and make compile client
make -j2

<img width="753" alt="image" src="https://github.com/ggg4566/Havoc_windows/assets/7532477/0114afc3-a6d0-4b54-afcc-fadcc61d312f">

Qt creator open cmake mingw project directory and compile
<img width="1427" alt="image" src="https://github.com/ggg4566/Havoc_windows/assets/7532477/bdaed753-d162-4941-9872-5a50e3494d24">

<img width="1429" alt="image" src="https://github.com/ggg4566/Havoc_windows/assets/7532477/c6f91e8e-24a7-4128-bddd-e6e2c39aa5e4">
