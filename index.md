## [cura build](https://github.com/Ultimaker/cura-build)
1. cmake 설치
2. git 설치
3. subversion aka svn


## Installation CURA on local Windows machine

1. Microsoft Visual Studio 2015 (Recommended) - Download Microsoft Visual Studio from [here (Web Installer)](https://go.microsoft.com/fwlink/?LinkId=532606&clcid=0x409) or [here (ISO Image)](https://go.microsoft.com/fwlink/?LinkId=615448&clcid=0x409).
2. [MinGW-w64](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe/download) 설치
- 설치를 할때 "select Architecture: i686 for 32bit or x86_64 for 64bit systems"
- 설치 폴더가 "C:\Program Files\mingw-w64\x86_64-8.1.0-posix-seh-rt_v6-rev0\mingw64\bin (or the i686 equivalent)" 나오게끔 위의 설정을 바꾼다.
3. [Python 3.5](https://www.python.org/downloads/release/python-3510/) 를 설치.
4. command에서 다음의 명령어를 순서대로 실행한다.
```
set cbe_src_dir=<where-your-source-dir-is>
set cbe_install_dir=<where-you-want-to-install>

cd %cbe_src_dir%
mkdir build
cd build

..\env_win64.bat

cmake -DCMAKE_BUILD_TYPE=Release ^
      -DCMAKE_INSTALL_PREFIX=%cbe_install_dir% ^
      -DCMAKE_PREFIX_PATH=%cbe_install_dir% ^
      -G "NMake Makefiles" ^
      ..
nmake

```




## Linux
### Install Dependencies
```
sudo apt-get update
sudo apt install cmake git subversion

```
### Install Docker
```
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
### Build Docker Image
```
cd /home/mingyu/Downloads
git clone https://github.com/Ultimaker/cura-build-environment
cd cura-build-environment
sudo docker pull ultimaker/cura-build-environment
sudo docker build -t cura-build-env -f docker/linux/Dockerfile.centos .
```

