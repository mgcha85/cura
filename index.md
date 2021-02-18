## [cura build](https://github.com/Ultimaker/cura-build)
1. cmake 설치
2. git 설치
3. subversion aka svn


## [cura build environment](https://github.com/Ultimaker/cura-build-environment)
```
cd C:\Users\ROKIT\Documents
git clone https://github.com/Ultimaker/cura-build-environment
cd cura-build-environment
docker pull ultimaker/cura-build-environment

1. docker/windows/Dockerfile.vs2015 파일에서 1809 을 1607로 바꾼다. (crlt+H)
2. 아래 코드를 build.ps1에 삽입
ExternalProject_Add(myProj
  GIT_REPOSITORY  https://github.com/my/project
  GIT_CONFIG      http.sslVerify=false
)

docker build -t cura-build-env -f docker/windows/Dockerfile.vs2015 .
.\scripts\python3.5\windows\build.ps1
```


## Installation CURA on local Windows machine
```
1. Microsoft Visual Studio 2015 (Recommended) - Download Microsoft Visual Studio from [here (Web Installer)](https://go.microsoft.com/fwlink/?LinkId=532606&clcid=0x409) or [here (ISO Image)](https://go.microsoft.com/fwlink/?LinkId=615448&clcid=0x409).
2. [MinGW-w64](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe/download)
- 설치를 할때 "select Architecture: i686 for 32bit or x86_64 for 64bit systems"
- 설치 폴더가 "C:\Program Files\mingw-w64\x86_64-8.1.0-posix-seh-rt_v6-rev0\mingw64\bin (or the i686 equivalent)" 나오게끔 위의 설정을 바꾼다.
3. [Python 3.5](https://www.python.org/downloads/release/python-3510/) 를 설치.
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

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/mgcha85/cura/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mgcha85/cura/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
