---
layout: post
date: 2024-06-29
title: "Unreal Engine 5.4 [1]: Introduction"
tags: [Unreal Engine, settings, ]
categories: [Unreal Engine, ]
---



## Unreal Engine 5.4?


---


![0](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/0.png)



## **Installing Unreal Engine 5.4**


---



### 0. Hardware / Software Spec


---


MacBook Pro M3 Pro


Mem 18 GB / Macintosh HD


MacOS Sonoma 14.4.1


---


Xcode Version 15.4


Command Line Tools for Xcode 15.3


---


EpicInstaller 15.17.1


Epic Games Launcher 16.7.1


Unreal Engine 5.4



### 1. Install Xcode


Android Studio of JetBrains or Visual Studio for Mac of MS also **require** **Xcode** to be installed to finally compile software for iOS/macOS, and Game Maker, Unity, Unreal Engine, and React Native also **require Xcode** to compile into the iOS environment.


If there is no Xcode on MacOS, the following error message will appear even if you installed UE.


![1](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/1.png)


As said above, we need to download and install Xcode for Unreal Engine. The Xcode application may need to be moved to your application folder on your Mac for UE to begin loading. 


There are two ways to do this. 



#### 1-1) **Download via the App Store for the latest version**


**Open the App Store on your mac > Sign in > Search for ‘Xcode’ > Click ‘install or update’**


![2](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/2.png)_Download Xcode via App Store 🍎_


_* If you can’t download it from the App store then find the download on Apples website._



#### 1-2) **Download via the Developer site for a specific version (recommended)**


['Downloads' of Apple Developer Website](https://developer.apple.com/download/) **> Sign in > ‘**[**More**](https://developer.apple.com/download/all/)**’ Section > Type in the version and download** **`Xcode _`**_**`.`**_**`_.xip`** **file > Extract** **`.xip`** **file > Drag application to the Applications folder (could be automatic)**


**Xcode** is a large application (Xcode 15.4 is 3.19 GB), so this will take awhile depending on your internet connection.


![3](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/3.png)_Xcode Installed! 😆_



#### 2) **Install the Command Line Tool (CLT)**


['Downloads' of Apple Developer Website](https://developer.apple.com/download/) **> Sign in > ‘**[**More**](https://developer.apple.com/download/all/)**’ Section > Type in ‘Command Line Tool’ and download** **`Command Line Tools for Xcode __._.dmg`** **file > Extract and install**


It’s a large file (around 4GB), so please make sure your device has enough storage and check if the internet connection is stable.


Proceed with the installation carefully by following the instructions! 🫰


![4](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/4.png)_Almost done! 👏_


If you've never installed **Xcode** before, instead of visiting the developer website, you can update **CLT** using the terminal with `xcode-select --install` command.


However, if you have an existing **Xcode** installed, you may see the following error:



{% raw %}
```text
xcode-select: error: Command line tools are already installed. Use “Software Update” to install updates.
```
{% endraw %}



This means you gotta to go to the developer's website to install it.



#### 3) Delete downloaded files


Let’s delete the `.xip` and `.dmg` files just downloaded since we probably will not going to need it anymore! 👋



### 2. Install Unreal Engine


[**Unreal Engine Download Website**](https://www.unrealengine.com/ko/download)



#### **1) Instructions for Epic Games Launcher**

1. [**Steps for installing Unreal Engine**](https://dev.epicgames.com/documentation/en-us/unreal-engine/installing-unreal-engine)
2. [**Steps for installing Unreal Engine from the source code**](https://dev.epicgames.com/documentation/en-us/unreal-engine/downloading-unreal-engine-source-code?application_version=5.4)
3. [**Installing Unreal Engine Video**](https://youtu.be/rldy9yY0yDU?si=pi8ApOu6B1IwnLSQ)

If you install the Unreal Engine following the instructions above, you will be able to open the **Epic Games Launcher**.



#### 2) Installation for Unreal Engine


**Go to ‘Unreal Engine’ on left sidebar > ‘Library’ on the tab above > ‘ENGINE VERSIONS’ > Install the ‘Unreal Engine’**


![5](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/5.png)_Downloading Unreal Engine via Epic Games Launcher 🎮_



#### 3) “Xcode Not Found” Error Again…


![6](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/6.png)_I thought I did all that it requires… 🤔_


The `Xcode Not Found` error message says to run the `xcode-select command-line-tool` to specify the location but it didn’t work..


So, I thought, I need to run the command below to set the location of the Xcode application since I didn’t set it before at all.



{% raw %}
```bash
sudo xcode-select -s /Applications/Xcode.app
```
{% endraw %}



![7](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/7.png)


> 👸 _**Keep the Xcode open!!!**_


And then…. The **Unreal Editor** worked well! The message left below that was saying ‘Initializing…’ started to count the percentage.


![8](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/8.png)_It works! 😚_



#### 4) Done!


This is the first scene that you can see on the **Unreal Project Browser**.


![9](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/9.png)_Finally~~ 😉_



## What do you want to do with UE? 🤩


---


As finalizing my introduction to the **Unreal Engine**, I am considering creating a Project for **Virtual Production** in the **FILM / VIDEO & LIVE EVENTS** section.


The **Virtual Production** project template contains functionality for Virtual Reality Scouting, Virtual Camera, SDI(Serial Digital Interface) Video, Live Compositing and nDisplay.


![10](/assets/img/2024-06-29-Unreal-Engine-5.4-[1]:-Introduction.md/10.png)_A Project for Virtual Production in the FILM / VIDEO & LIVE EVENTS section._


Let's continue in the next posting! 💝



## References


---

- [https://www.freecodecamp.org/news/how-to-download-and-install-xcode/](https://www.freecodecamp.org/news/how-to-download-and-install-xcode/)
- [https://www.unrealengine.com/ko/download](https://www.unrealengine.com/ko/download)
