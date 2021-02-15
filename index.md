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
