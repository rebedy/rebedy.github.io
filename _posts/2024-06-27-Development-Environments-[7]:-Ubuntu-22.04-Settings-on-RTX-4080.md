---
layout: post
date: 2024-06-27
title: "Development Environments [7]: Ubuntu 22.04 Settings on RTX 4080"
tags: [settings, Ubuntu 22.04, ]
categories: [Development Environments, ]
---


> 👸 **In conclusion, I later installed Ubuntu 20.04 by following the link in Prerequisites.  
> However, I am just sharing the installation details of version 22.04.**



## **Prerequisites**


---

- 


## Trial #1


---



#### **Bluetooth**

- Install Blueman in Ubuntu 22.04
- [https://installati.one/install-blueman-ubuntu-22-04/](https://installati.one/install-blueman-ubuntu-22-04/)


#### **CUDA Installation   → 11.8**

- [https://velog.io/@younder/%EB%94%A5%EB%9F%AC%EB%8B%9D%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%99%98%EA%B2%BD%EA%B5%AC%EC%84%B1-CUDACUDNN](https://velog.io/@younder/%EB%94%A5%EB%9F%AC%EB%8B%9D%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%99%98%EA%B2%BD%EA%B5%AC%EC%84%B1-CUDACUDNN)
- [https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local](https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local)
- [https://webnautes.tistory.com/1765](https://webnautes.tistory.com/1765)
- [https://docs.nvidia.com/deeplearning/frameworks/pytorch-release-notes/rel-22-09.html#rel-22-09](https://docs.nvidia.com/deeplearning/frameworks/pytorch-release-notes/rel-22-09.html#rel-22-09)
- cudnn check
	- cat /usr/local/cuda/include/cudnn_version.h | grep CUDNN_MAJOR -A 2

	> #define CUDNN_MAJOR 8  
	> #define CUDNN_MINOR 8  
	> #define CUDNN_PATCHLEVEL 1


		#define CUDNN_VERSION (CUDNN_MAJOR * 1000 + CUDNN_MINOR * 100 + CUDNN_PATCHLEVEL)


	/* cannot use constexpr here since this is a C-only file */



#### **nvidia-smi**

- initially, I have CUDA version 12:0


#### **CUDA Reinstall**

- [https://velog.io/@cosmos42/Ubuntu-2204-RTX-3090-CUDA](https://velog.io/@cosmos42/Ubuntu-2204-RTX-3090-CUDA)


#### **When nvcc doesn’t work**

- [https://yoonchang.tistory.com/27](https://yoonchang.tistory.com/27)


#### **nvcc -V**


> nvcc: NVIDIA (R) Cuda compiler driver  
> Copyright (c) 2005-2022 NVIDIA Corporation  
> Built on Wed_Sep_21_10:33:58_PDT_2022  
> Cuda compilation tools, release 11.8, V11.8.89  
> Build cuda_11.8.r11.8/compiler.31833905_0



#### **Still nvidia-smi CUDA version 12:0**



#### **When nvcc and nvidia-smi are different even though you reinstalled CUDA**

- [https://stackoverflow.com/questions/53422407/different-cuda-versions-shown-by-nvcc-and-nvidia-smi](https://stackoverflow.com/questions/53422407/different-cuda-versions-shown-by-nvcc-and-nvidia-smi)
- [https://bo-10000.tistory.com/73](https://bo-10000.tistory.com/73)
- **No worries.** Usually, version from nvidia-smi is one step higher than that of nvcc. It is in regard to the binary files for cuda operation.

---



#### **Anaconda**

- [https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-22-04](https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-22-04)
- sha256sum [anaconda.sh](http://anaconda.sh/)


{% raw %}
```javascript
fedf9e340039557f7b5e8a8a86affa9d299f5e9820144bd7b92ae9f7ee08ac60  [anaconda.sh](http://anaconda.sh/)
```
{% endraw %}


- conda —version
	- conda 4.5.11
- conda create -n init
	- python 3.8
	- pip install torch==1.12.0+cu116 torchvision==0.13.0+cu116 torchaudio==0.12.0 --extra-index-url https://download.pytorch.org/whl/cu116


#### **Torch**

- `pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118`
- **Torch-tensorRT**
	- [https://pytorch.org/TensorRT/tutorials/installation.html](https://pytorch.org/TensorRT/tutorials/installation.html)


#### **Sklearn**

- [https://itslinuxfoss.com/module-not-found-error-no-module-named-sklearn-python/#3:~:text=Solution 2%3A Install the sklearn Module in Python (For Linux)](https://itslinuxfoss.com/module-not-found-error-no-module-named-sklearn-python/#3:~:text=Solution%202%3A%20Install%20the%20sklearn%20Module%20in%20Python%20(For%20Linux))


#### **OpenCV**

- [https://idroot.us/install-opencv-ubuntu-22-04/](https://idroot.us/install-opencv-ubuntu-22-04/)

---


⬇️

- 이 [셋팅](https://leonam.tistory.com/98)으로 추후 변경해야할 가능성 높음. torch 2.0은 너무 최신이다. 지원하지 않는 부분들이 많을 가능성.
	- cuda 11.3 / cudnn 8.2.1 / torch 1.11.1

⬇️


---



## **Ubuntu 22.04 Development Environment Settings on RTX 4080** 


---



#### **BIOS/UEFI**


F4 / F12 with or w/o Ctrl



#### **Ubuntu Reinstall**

- [https://velog.io/@se0yeon00/엔비디아-드라이버-설치의-국룰](https://velog.io/@se0yeon00/%EC%97%94%EB%B9%84%EB%94%94%EC%95%84-%EB%93%9C%EB%9D%BC%EC%9D%B4%EB%B2%84-%EC%84%A4%EC%B9%98%EC%9D%98-%EA%B5%AD%EB%A3%B0)
- [https://amkorousagi-money.tistory.com/entry/우분투-부팅-usb-설치-방법-우분투-설치-파티션-설정](https://amkorousagi-money.tistory.com/entry/%EC%9A%B0%EB%B6%84%ED%88%AC-%EB%B6%80%ED%8C%85-usb-%EC%84%A4%EC%B9%98-%EB%B0%A9%EB%B2%95-%EC%9A%B0%EB%B6%84%ED%88%AC-%EC%84%A4%EC%B9%98-%ED%8C%8C%ED%8B%B0%EC%85%98-%EC%84%A4%EC%A0%95)


#### **Bluetooth**

- Install Blueman in Ubuntu 20.04
- [https://linux.how2shout.com/how-to-install-blueman-on-linux-mint-or-ubuntu-20-04/](https://linux.how2shout.com/how-to-install-blueman-on-linux-mint-or-ubuntu-20-04/)


#### **Chrome**

- [https://chunggaeguri.tistory.com/entry/Ubuntu-2004-Ubuntu-Chrome-설치하기](https://chunggaeguri.tistory.com/entry/Ubuntu-2004-Ubuntu-Chrome-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0)


#### **Hardware information**



{% raw %}
```javascript
lspci | grep -i VGA
```
{% endraw %}




{% raw %}
```javascript
nvidia-smi --query | fgrep 'Product Name'
```
{% endraw %}


- **NVIDIA GeForce RTX 4080**


#### **GCC Complier**



{% raw %}
```javascript
sudo apt install build-essential
```
{% endraw %}




{% raw %}
```javascript
gcc --version
```
{% endraw %}



> gcc (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0  
> Copyright (C) 2019 Free Software Foundation, Inc.  
> This is free software; see the source for copying conditions.  There is NO  
> warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.



#### **Nvidia Driver Installation**

- **우분투 리눅스 20.04 에서 nvidia driver, cuda 설치오류 – nouveau 커널 드라이버 제거**[https://blog.boxcorea.com/wp/archives/3323](https://blog.boxcorea.com/wp/archives/3323)
- [https://sseongju1.tistory.com/10](https://sseongju1.tistory.com/10)
- **version check**

	
{% raw %}
```javascript
	**sudo cat /proc/driver/nvidia/version**
```
{% endraw %}


	- NVRM version: NVIDIA UNIX x86_64 Kernel Module  525.85.05  Sat Jan 14 00:49:50 UTC 2023
	GCC version:  gcc version 9.4.0 (Ubuntu 9.4.0-1ubuntu1~20.04.1)


#### **CUDA Installation   → 11.3**


[https://jhrobotics.tistory.com/m/20](https://jhrobotics.tistory.com/m/20)  Ubuntu 20.04에 CUDA 11.3 cuDNN 8.2.1 설치하기



#### **CUDA Reinstall**

- 


#### **When nvcc doesn’t work**

- [https://yoonchang.tistory.com/27](https://yoonchang.tistory.com/27)
- **nvcc -V**

	> nvcc: NVIDIA (R) Cuda compiler driver  
	> Copyright (c) 2005-2022 NVIDIA Corporation  
	> Built on Wed_Sep_21_10:33:58_PDT_2022  
	> Cuda compilation tools, release 11.8, V11.8.89  
	> Build cuda_11.8.r11.8/compiler.31833905_0



#### **Still nvidia-smi CUDA version 12:0**

- **When nvcc and nvidia-smi are different even though you reinstalled CUDA**
	- [https://stackoverflow.com/questions/53422407/different-cuda-versions-shown-by-nvcc-and-nvidia-smi](https://stackoverflow.com/questions/53422407/different-cuda-versions-shown-by-nvcc-and-nvidia-smi)
	- [https://bo-10000.tistory.com/73](https://bo-10000.tistory.com/73)
	- **No worries.** Usually, version from nvidia-smi is one step higher than that of nvcc. It is in regard to the binary files for cuda operation.

---



#### **Anaconda**

- [https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-22-04](https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-22-04)
- sha256sum [anaconda.sh](http://anaconda.sh/)


{% raw %}
```javascript
fedf9e340039557f7b5e8a8a86affa9d299f5e9820144bd7b92ae9f7ee08ac60  [anaconda.sh](http://anaconda.sh/)
```
{% endraw %}


- conda —version
	- conda 4.5.11
- conda create -n init
	- python 3.8
	- pip install torch==1.12.0+cu116 torchvision==0.13.0+cu116 torchaudio==0.12.0 --extra-index-url https://download.pytorch.org/whl/cu116


#### **Mount HDD** 



{% raw %}
```javascript
sudo fdisk /dev/sda
```
{% endraw %}


- /dev/sda : original HDD address from ‘Disks’ program
- _The size of this disk is 3.6 TiB (4000787030016 bytes). DOS partition table format cannot be used on drives for volumes larger than 2199023255040 bytes for 512-byte sectors. Use GUID partition table format (GPT)._
- [https://seongkyun.github.io/others/2019/03/05/hdd_mnt/](https://seongkyun.github.io/others/2019/03/05/hdd_mnt/)

> Disk /dev/sda: 3.64 TiB, 4000787030016 bytes, 7814037168 sectors  
> Disk model: ST4000DM004-2U91  
> Units: sectors of 1 * 512 = 512 bytes  
> Sector size (logical/physical): 512 bytes / 4096 bytes  
> I/O size (minimum/optimal): 4096 bytes / 4096 bytes  
> Disklabel type: gpt  
> Disk identifier: 7AA54D54-0F34-49FD-9455-74DEC68BFB42



#### **Torch**

- `conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch`


#### **Torch-tensorRT**

- [https://pytorch.org/TensorRT/tutorials/installation.html](https://pytorch.org/TensorRT/tutorials/installation.html)
- **conda install ipython matplotlib numpy scipy tqdm**
- **pip install opencv-python**

---



#### **When Hangul doesn’t work**

- [https://osg.kr/archives/913](https://osg.kr/archives/913)
- [https://frankler.tistory.com/66](https://frankler.tistory.com/66)
- 영어는 지우고 ‘hangul’ 만 남기기
- IBUS로만 해도 된다.
- set the configurations with ‘hangul’ not ‘korean’.
- Reboot after both installation and system setting.


#### **Useful programs**

- **VSCode, PuTTY, FileZilla, AnyDesk**
- **Microsoft Office, Teams, Outllook, Xpad**
	- [https://itsmeit.biz/install-microsoft-office-on-ubuntu-20-04.html](https://itsmeit.biz/install-microsoft-office-on-ubuntu-20-04.html)


#### **KakaoTalk  → do not try**

- [https://velog.io/@solkimdev/%EC%9A%B0%EB%B6%84%ED%88%AC-22.04-LTS-%EC%B9%B4%EC%B9%B4%EC%98%A4%ED%86%A1-%EC%84%A4%EC%B9%98](https://velog.io/@solkimdev/%EC%9A%B0%EB%B6%84%ED%88%AC-22.04-LTS-%EC%B9%B4%EC%B9%B4%EC%98%A4%ED%86%A1-%EC%84%A4%EC%B9%98)


#### **Conda env Installation**

- opencv: [https://jainn.tistory.com/12](https://jainn.tistory.com/12)


#### **Anydesk**





