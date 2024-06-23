---
layout: post
date: 2024-06-24
title: "Development Environments [4]: Ubuntu 20.04 Settings on RTX 4080 - 3"
tags: [settings, Ubuntu 20.04, ]
categories: [Development Environments, ]
---



## **Prerequisites**


---

- [Development-Environments-2-Ubuntu-20.04-Settings-on-RTX-4080-1](https://rebedy.github.io/posts/Development-Environments-2-Ubuntu-20.04-Settings-on-RTX-4080-1/)
- [Development-Environments-3-Ubuntu-20.04-Settings-on-RTX-4080-2](https://rebedy.github.io/posts/Development-Environments-3-Ubuntu-20.04-Settings-on-RTX-4080-2/)


## **6. Anaconda on Ubuntu 20.04 🐍**


---



### **1) Download and install Anaconda**


Follow the steps to install the Anaconda distribution on the Ubuntu system. They are explained in detail below:



#### **Step 1. Visit** [**Anaconda website**](https://www.anaconda.com/download)


Visit the [**official website**](https://www.anaconda.com/download) of Anaconda distribution and download the latest version of Anaconda distribution installer for Ubuntu.



#### **Step 2. Send an email**


Provide an email to download Distribution of Anaconda.


![0](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/0.png)_Type in your email address to get the Distribution for Anaconda. 🐍_



#### **Step 3. Check an email**


Go to your inbox and check if there is an email from  **<account@anaconda.cloud>**.


If you see the link to download Anaconda and Conda packages, clik the ‘Download Now’ button!


![1](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/1.png)_This is what you will see on the email! 📧_


![2](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/2.png)_If you click ‘Download Now’ button from above, this link will be opened._


If you click the button, downlo ad will be proceeded automatically!



#### **Step 4. Open the terminal and run the installer**


Go to the `~/Download` directory and open the terminal with `Ctrl+Alt+T` or you can use the right-click on your mouse from the directory from the **`Files`** application. (You will see `Open in Terminal`)


Then run the Anaconda installer by executing the following command.



{% raw %}
```bash
bash Anaconda3-2024.02-1-Linux-x86_64.sh
```
{% endraw %}



![3](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/3.png)_Press ENTER for once and press Space bar till you see Chapter 15.12! ⏭️_


Press ENTER button once if you see the outcome like above then the license agreement will show up.


Then press space bar repeatedly to review the license agreement until you see Chapter “15.12 ENTIRE AFREEMENT.”.


Then yo will see as below:


![4](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/4.png)_Type ‘yes’ to continue… 🆗_



#### **Step 5. Specify the installation location**


After accepting the license agreement, the installer will ask for the installation folder for Anaconda distribution. You can press ‘Enter’ to install in the default location or you can specify your desired location. Then installer will start unpacking packages and install them. Installation may take some time.


![5](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/5.png)_Check the Anaconda location and press ENTER to confirm the location! ☑️_



#### **Step 6. Initialize Anaconda**


After installing Anaconda, the installer will ask the user to initialize the conda.


Since it was installed with `sudo`, it asks whether to configure `conda init` for `root`.


If you want to initialize the conda environment even as `root`, type “yes” to initialize Anaconda and finish installation.


It will add the ‘conda’ tool to the system path, so users can run it from any directory.


If this part is no longer needed, find `>>> conda initailize >>>` at the end of `/root/.bashrc` and remove it!


![6](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/6.png)_Type ‘yes’ and press ENTER_


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



![7](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/7.png)



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


![8](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/8.png)_Type ‘yes’ and press ‘ENTER’ to update Anaconda._



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
conda create --name {env_name} python=3.8
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
conda install ipython matplotlib numpy scipy tqdm
pip install opencv-python
```
{% endraw %}



> 👸 **TBC…** ⏩



## References


---

- [https://www.geeksforgeeks.org/how-to-install-anaconda-on-ubuntu-20-04/](https://www.geeksforgeeks.org/how-to-install-anaconda-on-ubuntu-20-04/)
- [https://velog.io/@boom109/Anaconda-설치-on-Ubuntu-20.04-LTS](https://velog.io/@boom109/Anaconda-%EC%84%A4%EC%B9%98-on-Ubuntu-20.04-LTS)
