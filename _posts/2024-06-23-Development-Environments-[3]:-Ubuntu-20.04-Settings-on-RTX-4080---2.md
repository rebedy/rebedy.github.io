---
layout: post
date: 2024-06-23
title: "Development Environments [3]: Ubuntu 20.04 Settings on RTX 4080 - 2"
tags: [settings, Ubuntu 20.04, ]
categories: [Development Environments, ]
---



## Prerequisites


---

- [Development-Environments-2-Ubuntu-20.04-Settings-on-RTX-4080-1/](https://rebedy.github.io/posts/Development-Environments-2-Ubuntu-20.04-Settings-on-RTX-4080-1/)


## 4. Install c**uda 11.3**


---



### 1) Download CUDA Toolkit 11.3


[NVIDIA DEVELOPER - CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive)


Go to website above in order to install **`cuda 11.3`**. 


![0](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/0.png)_Select target platform_


[CUDA Toolkit 11.3.1](https://developer.nvidia.com/cuda-11-3-1-download-archive) > Operating System ‘Linux’ > Architecture ‘x86_64’ > Distribution ‘Ubuntu’ > Version ‘20.04’ > Installer Type ‘runfile(local)’ > Follow the instruction


![1](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/1.png)_Instructions for the installation_



{% raw %}
```bash
# runfile(local)
wget https://developer.download.nvidia.com/compute/cuda/11.3.1/local_installers/cuda_11.3.1_465.19.01_linux.run
sudo sh cuda_11.3.1_465.19.01_linux.run
```
{% endraw %}



**OR**


If the instruction above doesn’t work then do below.



{% raw %}
```bash
# deb(local)
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin
sudo mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/11.3.1/local_installers/cuda-repo-ubuntu2004-11-3-local_11.3.1-465.19.01-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu2004-11-3-local_11.3.1-465.19.01-1_amd64.deb
sudo apt-key add /var/cuda-repo-ubuntu2004-11-3-local/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda
```
{% endraw %}




### 2) Install the CUDA Toolkit 11.3



#### (1) Run `sudo sh cuda_11.3.1_465.19.01_linux.run`


After downloading cuda linux `.run` file using `wget`, we need to run the `.run` file using `sh` command.


Run the command above. Make sure you are at the same directory as you run the `wget` command.


![2](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/2.png)_Move to ‘Continue’ and select with ENTER._


![3](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/3.png)_Type ‘accept’ and press ENTER._


![4](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/4.png)_Press ENTER on ‘Driver’ to dismiss it and select ‘Install’_


![5](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/5.png)_It will look like this when the installation went well! 🎊_



#### (2) gcc error


> 👸 _If the problem occurs because of the absence of gcc…_



{% raw %}
```bash
sudo apt update 
sudo apt install build-essential 
sudo apt-get install manpages-dev
gcc --version
```
{% endraw %}



> gcc (Ubuntu 9.4.0-1ubuntu1~20.04.2) 9.4.0  
> Copyright (C) 2019 Free Software Foundation, Inc.  
> This is free software; see the source for copying conditions.  There is NO  
> warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.



#### (3) Check CUDA version



{% raw %}
```bash
nvcc -V
```
{% endraw %}



![6](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/6.png)

- **If** **`nvcc`** **command is not found and error occurs…**
	- **Run** **`sudo apt install nvidia-cuda-toolkit`**

![7](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/7.png)_Command sudo apt install nvidia-cuda-toolkit is running!_



#### (4) Add CUDA Toolkit settings to environment variables



{% raw %}
```bash
sudo sh -c "echo 'export PATH=$PATH:/usr/local/cuda-11.3/bin'>> /etc/profile"
sudo sh -c "echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-11.3/lib64'>> /etc/profile"
sudo sh -c "echo 'export CUDARDIR=/usr/local/cuda-11.3'>> /etc/profile"
source /etc/profile
```
{% endraw %}




## 5. Install cuDNN


---



### 1) Download and install cuDNN


[NVIDIA cuDNN Downloads](https://developer.nvidia.com/cudnn-9-1-1-download-archive)


Go to the website above in order to install **`cuDNN Archive`** in order to specify the cuDNN version.


An NVIDIA account is required, so if you do not have one, you will need to sign up beforehand.
After log in to NVIDIA DEVELOPER website, download as indicated in below.



#### (1) To install cnDNN 9.x.x versions


![8](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/8.png)


[cuDNN 9.2.0 Downloads](https://developer.nvidia.com/cudnn-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=20.04&target_type=deb_local) > Operating System ‘Linux’ > Architecture ‘x86_64’ > Distribution ‘Ubuntu’ > Version ‘20.04’ > Installer Type ‘deb(local)’ > Follow the instruction


![9](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/9.png)_Press the ‘Download (1.4 GB)’ button._


If the download is done, run command below.



{% raw %}
```bash
wget https://developer.download.nvidia.com/compute/cudnn/9.2.0/local_installers/cudnn-local-repo-ubuntu2004-9.2.0_1.0-1_amd64.deb
sudo dpkg -i cudnn-local-repo-ubuntu2004-9.2.0_1.0-1_amd64.deb
sudo cp /var/cudnn-local-repo-ubuntu2004-9.2.0/cudnn-*-keyring.gpg /usr/share/keyrings/
sudo apt-get update
sudo apt-get -y install cudnn-cuda-11
```
{% endraw %}




#### (2) To install cnDNN 8.x.x ~ 1.x.x versions (in this case v8.2.1) ⭐


[NVIDIA cuDNN Archive](https://developer.nvidia.com/cudnn-archive)


Follow the instruction below! 🚶‍♀️


[**cuDNN 8.x - 1.x**](https://developer.nvidia.com/rdp/cudnn-archive) **(December 2023 - August 2014) >** [**Download cuDNN v8.2.1 (June 7th, 2021), for CUDA 11.x**](https://developer.nvidia.com/rdp/cudnn-archive#a-collapse821-113) **>** [**cuDNN Library for Linux (x86_64)**](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.2.1.32/11.3_06072021/cudnn-11.3-linux-x64-v8.2.1.32.tgz)


![10](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/10.png)



### 2) Unzip the downloaded file and check the setting

- **Copy command**


{% raw %}
```bash
cp {directory_or_file_to_copy} {directory_or_file_to_paste}
```
{% endraw %}


- **Decompression command**


{% raw %}
```bash
tar xvzf {compressed_filename}
```
{% endraw %}



* means all inclusive

- **RUN**


{% raw %}
```bash
tar xvzf cudnn-11.3-linux-x64-v8.2.1.32.tgz

sudo cp cuda/include/cudnn* /usr/local/cuda/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*

sudo ln -sf /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_adv_train.so.8.2.1 /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_adv_train.so.8
sudo ln -sf /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_ops_infer.so.8.2.1  /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_ops_infer.so.8
sudo ln -sf /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_cnn_train.so.8.2.1  /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_cnn_train.so.8
sudo ln -sf /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_adv_infer.so.8.2.1  /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_adv_infer.so.8
sudo ln -sf /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_ops_train.so.8.2.1  /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_ops_train.so.8
sudo ln -sf /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_cnn_infer.so.8.2.1 /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn_cnn_infer.so.8
sudo ln -sf /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn.so.8.2.1 /usr/local/cuda-11.3/targets/x86_64-linux/lib/libcudnn.so.8
```
{% endraw %}


- **Make sure**

Make sure the system can find newly added libraries and check if the setting is perfectly done.



{% raw %}
```bash
sudo ldconfig
ldconfig -N -v $(sed 's/:/ /' <<< $LD_LIBRARY_PATH) 2>/dev/null | grep libcudnn
```
{% endraw %}



![11](/assets/img/2024-06-23-Development-Environments-[3]:-Ubuntu-20.04-Settings-on-RTX-4080---2.md/11.png)






> 👸 **TBC…** ⏩



## References


---

- [https://ingu627.github.io/tips/install_cuda_linux/](https://ingu627.github.io/tips/install_cuda_linux/)
