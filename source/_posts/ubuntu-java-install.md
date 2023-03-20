---
title: ubuntu_java_install
date: 2023-03-20 18:33:55
tags:
---


## JDK 17

[Java SE 17 Archive Downloads](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)

+ [Linux x64 Compressed Archive -- 17.0.6](https://download.oracle.com/java/17/archive/jdk-17.0.6_linux-x64_bin.tar.gz)



## Steps

```shell
cd ~/download
wget https://download.oracle.com/java/17/archive/jdk-17.0.6_linux-x64_bin.tar.gz
tar -xzvf ./jdk-17.0.6_linux-x64_bin.tar.gz -C ~/local/java17/

cd ~
vim .profile
export JAVA_HOME=/home/pzd/local/java17/jdk-17.0.6
export PATH=$PATH:$JAVA_HOME/bin;
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar;
source .profile

java --version
# java 17.0.6 2023-01-17 LTS
# Java(TM) SE Runtime Environment (build 17.0.6+9-LTS-190)
# Java HotSpot(TM) 64-Bit Server VM (build 17.0.6+9-LTS-190, mixed mode, sharing)
```