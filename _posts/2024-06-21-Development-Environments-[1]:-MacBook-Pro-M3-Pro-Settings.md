---
layout: post
date: 2024-06-21
title: "Development Environments [1]: MacBook Pro M3 Pro Settings"
tags: [settings, MacBook Pro, M3 Pro, ]
categories: [Development Environments, ]
math: false
---



## MacBook Pro M3 Pro


---


![0](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/0.png)


**MacBook Pro M3 Pro**


**Mem 18 GB / Macintosh HD**


**MacOS Sonoma 14.4.1**


> 👸 **This is the first thing that I did for MacBook Pro M3 Pro setting!** 💻



## APP Installation


---



### 1. Install `homebrew`



{% raw %}
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
{% endraw %}




### 2. Add Homebrew to your PATH in `.zprofile`


![1](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/1.png)


![2](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/2.png)



{% raw %}
```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/dyanlee/.zprofile
```
{% endraw %}




{% raw %}
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```
{% endraw %}




#### Check Installation



{% raw %}
```bash
brew --version
```
{% endraw %}




### 3. Install Programs using `brew`



{% raw %}
```bash
brew install --cask visual-studio-code google-chrome iterm2 onedrive notion anydesk arc
```
{% endraw %}




### 4. Install Programs using App Store

- Microsofts Word, Excel, PowerPoint


### 5. Install Programs from Web site

- KakaoTalk
- Microsofts ‘new’ Teams


## Anaconda Installation


---



### 1. Download Anaconda 


[https://www.anaconda.com/download](https://www.anaconda.com/download)


![3](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/3.png)



### 2. Install .pkg file


`Anaconda3-2023.09-0-MacOSX-arm64.pkg`


![4](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/4.png)


![5](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/5.png)


![6](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/6.png)



### 3. Make a virtual environment



{% raw %}
```bash
conda create -n {env_name}
```
{% endraw %}




### 4. Install libraries



#### **Scientific usage**



{% raw %}
```bash
conda install numpy scipy pandas
```
{% endraw %}




#### **ML & DL**



{% raw %}
```bash
conda install scikit-learn tensorflow
conda install -c pytorch pytorch torchvision
```
{% endraw %}




#### **Image Processing**



{% raw %}
```bash
conda install pillow scikit-image opencv
```
{% endraw %}




#### **Medical Image Processing**



{% raw %}
```bash
conda install -c conda-forge pydicom nibabel
conda install -c conda-forge simpleitk
```
{% endraw %}




#### **Visualization**



{% raw %}
```bash
conda install matplotlib seaborn
```
{% endraw %}




#### Tools



{% raw %}
```bash
conda install tqdm
```
{% endraw %}




## Settings


---



### 1. AirDrop


![7](/assets/img/2024-06-21-Development-Environments-[1]:-MacBook-Pro-M3-Pro-Settings.md/7.png)

- Click random place on the Finder window and go to `Customize Toolbar...`
- Add AirDrop to wherever you want to put it


### 2.  Dock Setting

- `System Settings > Desktop & Dock > Dock > Size`
- Adjust size of Dock bar
