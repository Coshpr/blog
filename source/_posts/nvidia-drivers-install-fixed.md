---
title: nvidia drivers install & fixed
date: 2023-03-30 15:39:43
tags: ['linux','nvidia']
---


## nvidia-smi and nvcc -V
>
> [显卡，显卡驱动,nvcc, cuda driver,cudatoolkit,cudnn到底是什么？--知乎](https://zhuanlan.zhihu.com/p/91334380)
CUDA 有两种API，即 Runtime API 与 Driver API。

+ nvidia-smi : GPU 驱动版本型号 、 CUDA Driver API型号
+ nvcc -V  : CUDA Runtime API。

> nvidia-smi版本大于nvcc -V的版本不会有什么问题

![示意图](https://pic3.zhimg.com/80/v2-a1f1d9f699697a8e05979abf749fbeae_1440w.webp)

## Install

```bash
# 查看系统内核版本
cat /proc/version

# 查看显卡型号
lspci | grep -i nvidia
lshw -c video

# 查看是否有显卡驱动，有的会显示
nvidia-smi

# 禁用nouveau并重启
#（安装Nvidia显卡的官方驱动和系统自带的nouveau驱动冲突）
# 如果有输出说明nouveau正在加载，参考引文的方法禁用nouveau
lsmod | grep nouveau

# ubuntu-drivers devices
# sudo ubuntu-drivers autoinstall

## 卸载旧版本驱动
#之前通过ppa安装的，卸载如下
sudo apt-get remove --purge nvidia*
#以前是通过runfile安装的，卸载如下：
sudo ./NVIDIA-Linux-x86_64-384.59.run --uninstall

# 使用官方的NVIDIA驱动进行手动安装
# https://www.nvidia.com/Download/index.aspx
cd download/
wget -c https://cn.download.nvidia.com/XFree86/Linux-x86_64/525.89.02/NVIDIA-Linux-x86_64-525.89.02.run
sudo chmod a+x NVIDIA-Linux-x86_64-525.89.02.run 
sudo ./NVIDIA-Linux-x86_64-525.89.02.run -no-opengl-files -no-nouveau-check

nvidia-smi

```

## 参考

<https://blog.csdn.net/sinat_34686158/article/details/106845208>

<https://www.nvidia.com/Download/index.aspx>
