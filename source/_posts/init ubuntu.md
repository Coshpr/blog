---
title: init ubuntu
---


## install minconda

<https://docs.conda.io/en/latest/miniconda.html#linux-installers>

``` bash
cd ~
mkdir download
cd download
wget https://repo.anaconda.com/miniconda/Miniconda3-py310_23.1.0-1-Linux-x86_64.sh
bash Miniconda3-py310_23.1.0-1-Linux-x86_64.sh

# install default
```

> Note:<https://blog.csdn.net/netgc/article/details/124999614>

AlmaLinux OS 基金会自豪地宣布 AlmaLinux OS 9.0 正式发布。AlmaLinux 9 支持以下 4 种架构，与上游完全对等：
● Intle/AMD (x86_64)
● ARM64 (aarch64)
● IBM PowerPC (ppc64le)
● IBM Z (s390x)

## install nodejs

reference:  <https://developer.aliyun.com/article/760687>

```bash
sudo apt update
sudo apt install nodejs npm

# install nvm 
# https://github.com/nvm-sh/nvm?spm=a2c4e.10696291.0.0.a21e19a4sciOjR#installing-and-updating
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
# source ~/.bashrc

# 想要获取一系列 Node.js 版本，你可以使用nvm，运行：
nvm list-remote

# 想要安装最新可用的 Node.js，运行：
nvm install node

# 安装最新的长期版本和版本10.9.0:
nvm install --lts
nvm install 10.9.0

# 输入以下代码列出安装的 Node.js 版本
nvm ls

# 如果你想修改当前使用的版本，输入：
nvm use 12.16.3
```

## install hexo

``` bash
npm install -g hexo-cli

# Create pages and articles with the hexo new [layout] <title> command. For example, to create an "about me" page, run:
hexo new page about


# This will create a new file in source/about/index.md Similarly, you can create a new article with
# source/_posts/hello-world.md.
hexo new post "hello world"

# Run: hexo generate and hexo server
hexo generate
hexo server
```

### theme

+ [cactus](https://github.com/probberechts/hexo-theme-cactus) [demo](https://probberechts.github.io/hexo-theme-cactus/)

## Usage Nginx

```
sudo nginx -s reload
```

## Bugs & solution

+ Could not get lock /var/lib/dpkg/lock-frontend

```bash
sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock*
sudo dpkg --configure -a
sudo apt update
```
