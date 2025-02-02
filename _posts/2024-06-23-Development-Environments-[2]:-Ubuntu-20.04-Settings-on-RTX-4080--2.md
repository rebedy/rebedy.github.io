---
layout: post
date: 2024-06-23
title: "Development Environments [2]: Ubuntu 20.04 Settings on RTX 4080 -2"
tags: [settings, Ubuntu 20.04, ]
categories: [Development Environments, ]
math: false
---



## Prerequisites


---

- [Development-Environments-2-Ubuntu-20.04-Settings-on-RTX-4080-1/](https://rebedy.github.io/posts/Development-Environments-2-Ubuntu-20.04-Settings-on-RTX-4080-1/)


## 4. Install c**uda 11.3**


---



### 1) Download CUDA Toolkit 11.3


[NVIDIA DEVELOPER - CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive)


Go to website above in order to install **`cuda 11.3`**. 


![0](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/0.png)_Select target platform_


[CUDA Toolkit 11.3.1](https://developer.nvidia.com/cuda-11-3-1-download-archive) > Operating System ‘Linux’ > Architecture ‘x86_64’ > Distribution ‘Ubuntu’ > Version ‘20.04’ > Installer Type ‘runfile(local)’ > Follow the instruction


![1](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/1.png)_Instructions for the installation_



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


![2](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/2.png)_Move to ‘Continue’ and select with ENTER._


![3](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/3.png)_Type ‘accept’ and press ENTER._


![4](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/4.png)_Press ENTER on ‘Driver’ to dismiss it and select ‘Install’_


![5](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/5.png)_It will look like this when the installation went well! 🎊_



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



![6](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/6.png)

- **If** **`nvcc`** **command is not found and error occurs…**
	- **Run** **`sudo apt install nvidia-cuda-toolkit`**

![7](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/7.png)_Command sudo apt install nvidia-cuda-toolkit is running!_

- **No /usr/local/cuda-{version} directory after CUDA installation**


{% raw %}
```bash
sudo ln -s /usr /usr/local/cuda-{version}
```
{% endraw %}




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


![8](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/8.png)


[cuDNN 9.2.0 Downloads](https://developer.nvidia.com/cudnn-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=20.04&target_type=deb_local) > Operating System ‘Linux’ > Architecture ‘x86_64’ > Distribution ‘Ubuntu’ > Version ‘20.04’ > Installer Type ‘deb(local)’ > Follow the instruction


![9](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/9.png)_Press the ‘Download (1.4 GB)’ button._


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


![10](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/10.png)



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



![11](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/11.png)



### 3) Validation!!



{% raw %}
```bash
#!/bin/bash

# libraries for examples
sudo apt-get install libfreeimage3 libfreeimage-dev

cp -r /usr/src/cudnn_samples_v8/ $HOME

cd  $HOME/cudnn_samples_v8/mnistCUDNN

make clean && make

./mnistCUDNN

# Test passed!
```
{% endraw %}




## **6. Anaconda on Ubuntu 20.04 🐍**


---



### **1) Download and install Anaconda**


Follow the steps to install the Anaconda distribution on the Ubuntu system. They are explained in detail below:



#### **Step 1. Visit** [**Anaconda website**](https://www.anaconda.com/download)


Visit the [**official website**](https://www.anaconda.com/download) of Anaconda distribution and download the latest version of Anaconda distribution installer for Ubuntu.



#### **Step 2. Send an email**


Provide an email to download Distribution of Anaconda.


![12](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/12.png)_Type in your email address to get the Distribution for Anaconda. 🐍_



#### **Step 3. Check an email**


Go to your inbox and check if there is an email from  **<account@anaconda.cloud>**.


If you see the link to download Anaconda and Conda packages, clik the ‘Download Now’ button!


![13](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/13.png)_This is what you will see on the email! 📧_


![14](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/14.png)_If you click ‘Download Now’ button from above, this link will be opened._


If you click the button, downlo ad will be proceeded automatically!



#### **Step 4. Open the terminal and run the installer**


Go to the `~/Download` directory and open the terminal with `Ctrl+Alt+T` or you can use the right-click on your mouse from the directory from the **`Files`** application. (You will see `Open in Terminal`)


Then run the Anaconda installer by executing the following command.



{% raw %}
```bash
bash Anaconda3-2024.02-1-Linux-x86_64.sh
```
{% endraw %}



![15](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/15.png)_Press ENTER for once and press Space bar till you see Chapter 15.12! ⏭️_


Press ENTER button once if you see the outcome like above then the license agreement will show up.


Then press space bar repeatedly to review the license agreement until you see Chapter “15.12 ENTIRE AFREEMENT.”.


Then yo will see as below:


![16](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/16.png)_Type ‘yes’ to continue… 🆗_



#### **Step 5. Specify the installation location**


After accepting the license agreement, the installer will ask for the installation folder for Anaconda distribution. You can press ‘Enter’ to install in the default location or you can specify your desired location. Then installer will start unpacking packages and install them. Installation may take some time.


![17](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/17.png)_Check the Anaconda location and press ENTER to confirm the location! ☑️_



#### **Step 6. Initialize Anaconda**


After installing Anaconda, the installer will ask the user to initialize the conda.


Since it was installed with `sudo`, it asks whether to configure `conda init` for `root`.


If you want to initialize the conda environment even as `root`, type “yes” to initialize Anaconda and finish installation.


It will add the ‘conda’ tool to the system path, so users can run it from any directory.


If this part is no longer needed, find `>>> conda initailize >>>` at the end of `/root/.bashrc` and remove it!


![18](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/18.png)_Type ‘yes’ and press ENTER_


Now installation is complete and to activate Anaconda, just close the terminal and reopen it.



{% raw %}
```bash
(base) dyan@dyan-Z790-GAMING-X:~/Downloads$
```
{% endraw %}




### **2) Check** **`conda`** **version**


Run ‘conda info’ in the new terminal to verify that the Anaconda distribution is installed properly. It will display the details of installation if it is installed successfully.



{% raw %}
```bash
conda info
```
{% endraw %}



![19](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/19.png)



### 3) **Updating Anaconda**


It is very important to keep the Anaconda updated to the latest version.


**Step 1: Run conda update command**


Run the following command in the terminal.



{% raw %}
```bash
conda update --all
```
{% endraw %}



**Step 2: Confirm updates**


![20](/assets/img/2024-06-23-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--2.md/20.png)_Type ‘yes’ and press ‘ENTER’ to update Anaconda._



### **4)** **`conda`** **initialization and auto activation**


**`conda init`** adds the process of initializing `conda` to `/home/{user}/.bashrc`. 



{% raw %}
```bash
source /usr/anaconda3/bin/activate 
conda init
source ~/.bashrc
```
{% endraw %}



**`conda`** environment auto activation can be controlled using the following command.



{% raw %}
```bash
# Automatically activate conda environment (initial setup)
conda config --set auto_activate_base True

# Disable automatic activation of conda environment
conda config --set auto_activate_base False
```
{% endraw %}




### **5) Create new env**


Create new `conda` environment for each of your projects! ♻️



{% raw %}
```bash
conda create -n {env_name}
```
{% endraw %}



You also can specify the python version as below:



{% raw %}
```bash
conda create --name {env_name} python=3.8.19
```
{% endraw %}



> 👸 **I'd recommend that you create a dedicated** **`conda`** **environment for each project!** 👍



### 6) Activate and deactivate



{% raw %}
```bash
# When you activate the env you created from above
dyan@dyan-Z790-GAMING-X:~/$ conda activate {env_name}
({env_name}) dyan@dyan-Z790-GAMING-X:~/$ 

# When you deactivate the env you created from above
({env_name}) dyan@dyan-Z790-GAMING-X:~/$ conda deactivate
dyan@dyan-Z790-GAMING-X:~/$
```
{% endraw %}




### 7) Clone existing `conda` env



{% raw %}
```bash
conda create -n {env_name} --clone {existing_env_name}
```
{% endraw %}




### 8) Cleaning caches


If you repeatedly create various `conda` environments and install and delete `conda` packages, unnecessary package **caches** may accumulate in `{anaconda installation location}/pkgs/` and capacity may become an issue.



{% raw %}
```bash
du -h -s --apparent-size /home/dyan/anaconda3/pkgs/

# 5.3G   /home/dyan/anaconda3/pkgs/
```
{% endraw %}



Cleaning can be done using the conda command.



{% raw %}
```bash
conda clean -p
```
{% endraw %}



If `conda` does not operate normally after `conda` package cleaning, add the `-all` option as shown below to remove all **index cache, lock files, unused cache packages, and tarballs**.



{% raw %}
```bash
conda clean -all
```
{% endraw %}




## **7. Install Python packages**


---



### **1) Install** **`pip`** 



{% raw %}
```bash
sudo apt install python3-pip
```
{% endraw %}



> 👸 **And then let’s activate** **`conda`** **env before we start to install python packages!**



### **2) Install PYTORCH framework and it’s packages**



#### **→** [**v1.12.1 Linux and Windows**](https://pytorch.org/get-started/previous-versions/) **(previous versions)**


**Conda**



{% raw %}
```bash
# CUDA 11.3
conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch
```
{% endraw %}



**Wheel (Recommanded)**



{% raw %}
```bash
# CUDA 11.3
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 torchaudio==0.12.1 --extra-index-url https://download.pytorch.org/whl/cu113
```
{% endraw %}




### **3)** [**Torch-tensorRT**](https://pytorch.org/TensorRT/tutorials/installation.html)



{% raw %}
```bash
pip3 install torch-tensorrt -f https://github.com/NVIDIA/Torch-TensorRT/releases
```
{% endraw %}




### 4) More useful packages



{% raw %}
```bash
conda install ipython matplotlib numpy tqdm pyyaml
pip install -U scikit-learn scipy albumentations 
pip install wandb
pip install opencv-python
conda install -n fld ipykernel --update-deps --force-reinstall
pip install paramiko
```
{% endraw %}



> 👸 **TBC…** ⏩



## References


---

- [https://ingu627.github.io/tips/install_cuda_linux/](https://ingu627.github.io/tips/install_cuda_linux/)
- [https://www.geeksforgeeks.org/how-to-install-anaconda-on-ubuntu-20-04/](https://www.geeksforgeeks.org/how-to-install-anaconda-on-ubuntu-20-04/)
- [https://velog.io/@boom109/Anaconda-설치-on-Ubuntu-20.04-LTS](https://velog.io/@boom109/Anaconda-%EC%84%A4%EC%B9%98-on-Ubuntu-20.04-LTS)
