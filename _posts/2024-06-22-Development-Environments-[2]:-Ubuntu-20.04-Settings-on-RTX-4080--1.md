---
layout: post
date: 2024-06-22
title: "Development Environments [2]: Ubuntu 20.04 Settings on RTX 4080 -1"
tags: [settings, Ubuntu 20.04, ]
categories: [Development Environments, ]
math: false
---



## **Development Environment Settings** 🏞️


---


Every time I boot the desktop with Ubuntu install, this kind of `FAILED` error message appears. It says `[FAILED] Failed to start NVIDIA Persistence Daemon`…💩


![0](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/0.png)_FAILED…_


No matter how much I searched, I couldn't find the cause. I tried various things, but the problem still couldn’t be solved.😵


I just thought there is something wrong with the graphics card connection, so I **unplugged the graphics card and insert it again**.


Now, I am going to reinstall Ubuntu 20.04 to recreate the development environment.


> 👸 **Please unplug and insert the Graphic card once before you start this!** 🔌



## 0. Hardware Spec


---


**[Labtop]** 💻


MacBook Pro M3 Pro


Mem 18 GB / Macintosh HD


MacOS Sonoma 14.4.1


---


**[Desktop]** 🖥️


**Graphic Card:** **NVIDIA GeForce RTX 4080** (This can support Cuda v 12.0)



## 1. **Create a bootable USB stick on MacOS for Ubuntu** 


---



### 1) Download [Ubuntu 20.04 LTS (Focal Fossa)](https://mirror.kakao.com/ubuntu-releases/20.04/)


![1](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/1.png)_Choose this if you are at all unsure 😆_


[64-bit PC (AMD64) desktop image](https://mirror.kakao.com/ubuntu-releases/20.04/ubuntu-20.04.6-desktop-amd64.iso)


Choose since you have a computer based on the AMD64 or EM64T architecture (e.g., Athlon64, Opteron, EM64T Xeon, Core 2).



### 2) Install **Homebrew**



#### (1) **Is Homebrew not installed?**


> 👸 **If you don’t use a password to log in to your Mac, you cannot install Homebrew**❗



{% raw %}
```bash
brew
```
{% endraw %}



If Homebrew is not installed, you will see:



{% raw %}
```shell
zsh: command not found: brew
```
{% endraw %}




#### (2) Install homebrew on your MacOS


The [Homebrew website](https://brew.sh/) provides an installation script that can be downloaded and run with a single command. This is the easiest way to install Homebrew. If the code below doesn't work, check the [Homebrew website](https://brew.sh/) to see if it has been changed.



{% raw %}
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
{% endraw %}



The command above will ask you to enter your Mac user password. This is the password you use to log in to your Mac. You won't see the characters you typed. When you are done typing please press enter.


![2](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/2.png)



#### (3) Add Homebrew to your PATH in `.zprofile`


![3](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/3.png)


![4](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/4.png)



{% raw %}
```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/dyanlee/.zprofile
```
{% endraw %}




#### (4) Check Installation


Let’s check the version of installed homebrew!



{% raw %}
```bash
(base) dyanlee@Dyans-MacBook-Pro ~ % brew --version
Homebrew 4.3.4
```
{% endraw %}




### 3) Install [**balenaEtcher**](https://etcher.balena.io/) **using Homebrew**


**balenaEtcher** is a free and open-source utility used for writing image files such as .iso and .img files, as well as zipped folders onto storage media to create live SD cards and USB flash drives. [[1](https://en.wikipedia.org/wiki/Etcher_(software))]


![5](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/5.png)


[Homebrew Formulae for balenaetcher](https://formulae.brew.sh/cask/balenaetcher)



{% raw %}
```bash
brew install --cask balenaetcher
```
{% endraw %}



![6](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/6.png)_balenaEtcher installed!_


![7](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/7.png)_Click ‘Open’ here!_


![8](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/8.png)_Tah-Dah!_



### 4) Creating a bootable Ubuntu USB stick with balenaEtcher


Etcher consists of three steps.



#### **Step 1. Flash from File**


This opens a file requester where you have to navigate to and select the `ISO` file you downloaded.


In this step, select the `ISO` file you downloaded earlier.



#### Step 2. Select Target


If a USB device is already connected, it will be automatically selected.


![9](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/9.png)_Choose USB_



#### Step 3. Flash!


It will be enabled when both the image and drive are selected. Like `Disk Utility`, **Etcher** requires low-level access to your storage hardware and prompts for a password after selection.


![10](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/10.png)


**If you see message saying ‘Flash Complete!’ then creating bootable USB stick is DONE!**



## 2. Install Ubuntu 20.04 LTS using **bootable USB stick**


---



### 1) Connect the Ubuntu bootable USB


Connect the Ubuntu bootable USB and restart the Desktop.


When you see the booting screen, press the **`F12`** button repeatedly to enter BIOS.


The button to enter BIOS varies depending on the motherboard. It is usually one of `F12`, `F2`, or `Del` and is written on the screen when booting.


And then, select **`UEFI`** and proceed with installation.


![11](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/11.png)_Select UEFI!_


Then you will see that all filesystem checks are in progress!


![12](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/12.png)_Checking disks_



### 2) Proceed with installation


Follow instructions below! 🙂



#### (1) Setting for language and select ‘Install Ubuntu’


![13](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/13.png)_(1) Setting for language and select ‘Install Ubuntu’_



#### (2) Setting for Keyboard layout and select ‘Continue’


![14](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/14.png)_(2) Setting for Keyboard layout and select ‘Continue’_



#### (3) Uncheck ‘Download updates while installing Ubuntu’


![15](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/15.png)_(3) Uncheck ‘Download updates while installing Ubuntu’_



#### (4) Check ‘Erase Ubuntu 20.04.x LTS and reinstall’ to delete previous Ubuntu


![16](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/16.png)_(4) Check ‘Erase Ubuntu 20.04.x LTS and reinstall’ to delete previous Ubuntu_



#### (5) Select ‘Continue’ for the warning


![17](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/17.png)_(5) Select ‘Continue’ for the warning_



#### (6) Setting for the location and select ‘Continue’


![18](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/18.png)_(6) Setting for the location and select ‘Continue’_



#### (7) Setting for the basic information and select ‘Continue’


![19](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/19.png)_(7) Setting for the basic information and select ‘Continue’_



#### (8) Installation proceed


![20](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/20.png)_(8) Installation proceed_



#### (9) Installation complete and restart the computer


![21](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/21.png)_(9) Installation complete and restart the computer_



#### (10) Remove the USB stick and press ENTER to proceed the booting


![22](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/22.png)_(10) Remove the USB stick and press ENTER to proceed the booting_



## 3. Install the graphic card drivers


---


After you finish installing Ubuntu 20.04 using a bootable USB stick, when the computer is restarted the resolution might be a little weird. (large icons, undoable dual monitor, and so on...) Even though you tried to change the resolution from the `Settings`, there may be no other options. 🤷‍♀️


![23](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/23.png)_No other options for the resolution setting and dual monitor setting is incapable._



### 1) Check the installable drivers.



{% raw %}
```bash
ubuntu-drivers devices
```
{% endraw %}



You can check the vendor of graphic card and installable drivers with the command above!


![24](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/24.png)_The vendor of graphic card and installable drivers._



### 2) Install the graphic card driver


Choose if you want to install the driver automatically or with specific version and select the version you want to install. And then you can install the driver with the commands below.



{% raw %}
```bash
# Install driver automatically
sudo ubuntu-drivers autoinstall

# Install driver with specific version
sudo apt install nvidia-driver-535
```
{% endraw %}



![Installing NVIDIA driver with specific version.
](https://prod-files-secure.s3.us-west-2.amazonaws.com/2f9301c6-943e-48b6-8669-160bb74cd747/9634c124-559c-4f53-ab3e-fd23590ffc19/25.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466V5NFIPB2%2F20250202%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20250202T082425Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEN%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJGMEQCIHqWk605x6iiw8qVbkmJqNiNpKKFMOhCvXbDUtntDPrrAiB%2BUQ0AmG7oBl44V2CRIHfb00v0rbpQbkwrqiN0A8dTRiqIBAjn%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F8BEAAaDDYzNzQyMzE4MzgwNSIMFRKW%2Fj42EViZ4Hx3KtwDxBH4oFTQVw3TrZW8Rr9Tyiril4wC%2BotZmNFUlqd1Jyw1KZSkCaP5Tjww5sWmWvNQLpm1Ii0s8GVin8r5R4gZkR4bk7DlDrE3UIqQh6xfL5nEqaWN2uyj6aoM42p59b81wXzzQHV%2FlPfeQQbsUdUlIbWeIjLnY3lhJIT%2Bn1Bvo6OTIBQ5hFZHfoJRlxr4PeheCNcv4pMoas%2B59PFKV4oyPDSBaBBDkqnu0U871HdASH9NGnmfiSxoxc7t9%2FPYA8NOpAI8J2QRLwrVDxCgP55f9rstMuklgcIbfECZ9OBhStNaeDQ4y7MEXoJdppNd29B7VBWOHBfwvFo6pqszPLmPGwzAUZgKpC%2FKMuA%2F1%2B4i55VTPX5c5jTU6kS%2Bsu%2BmuTXi648hW9CXIaQzvG2mOW54krWmb3weOgDv56Mor0%2B1GKk8zAYK19Xr9%2F3ltTRvmI%2BbAGlMVePBO0Ey%2BTIZfA%2F6pFIIYMxMtBBAkf77cSOY7je5sNSPLh329vlcNjYYrrq9bEOiJo5CcFBH%2Bsj663qp%2FwxPujrFZYdx1ZdRVHzX25JakaN4Y%2FVib%2FDxXYtEbRKuwolV8Adve5S%2BORN4zIR4Ycxgdd%2FK%2Fl4QP%2FW%2FNFlymm4NPea6VamCBml0CJEwoZz8vAY6pgGeN%2FEPX31wOso7w%2FFi6yCk6OP8Q2ZQWi8msdRIetAgPyFxBvROmZ2YcUuO5y7FhPO9m7TtNgg18qgK1MQKKNxvIGNNUQh9GjpdmV2bQ7vLFO9VyF164HTts816Do6nw5hbWindOcTdxqT1xUqzCcN%2FZaBWO6oziil7yz3uzeXQw9REHYNNPe9MJ6E7rHtm62q80Tw%2FZ35fAlMFGHblYj208Qbui%2Bj9&X-Amz-Signature=6956d83b9cc39551b0f37f44a1d913aebeb454b8b0f0f1c1e0138dc6f57f118b&X-Amz-SignedHeaders=host&x-id=GetObject)



### 3) Install the packages for NVIDIA kernel module


After installing the NVIDIA driver, we need to install the **`modprobe`** package that helps load the NVIDIA kernel module.



{% raw %}
```bash
sudo apt-get install dkms nvidia-modprobe
```
{% endraw %}



Finalize the installation with following commands.



{% raw %}
```bash
sudo apt update
sudo apt upgrade
# ...
sudo reboot
```
{% endraw %}



![25](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/25.png)_Processing sudo apt upgrade … takes a little while. ⏳_



### 4) Check if the installation went well!


After rebooting, run the following command to check whether the installation was successful. If the result comes out as shown in the figure below , then the installation was successful! 👏



{% raw %}
```bash
nvidia-smi
```
{% endraw %}



![26](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/26.png)_nvidia-smi result!_


And now, the dual monitor works and there are more options for the resolution settings.


![27](/assets/img/2024-06-22-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--1.md/27.png)_Dual monitor works and the resolution is fine! 🥳_


> 👸 **TBC…** ⏩



## References


---

- [https://www.igeeksblog.com/how-to-install-homebrew-on-mac/](https://www.igeeksblog.com/how-to-install-homebrew-on-mac/)
- [https://wscode.tistory.com/95](https://wscode.tistory.com/95)
- [https://ingu627.github.io/tips/install_cuda_linux/](https://ingu627.github.io/tips/install_cuda_linux/)
