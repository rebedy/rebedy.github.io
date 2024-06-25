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


## 8. Check I**nformation**


---



#### 1) Graphic Card



{% raw %}
```bash
lspci | grep -i VGA
# or
nvidia-smi --query | fgrep 'Product Name'
```
{% endraw %}



> **NVIDIA GeForce RTX 4080**



#### 2) LSB (Linux Standard Base) and Distribution Information



{% raw %}
```bash
lsb_release -a
```
{% endraw %}



> No LSB modules are available.  
> Distributor ID:	Ubuntu  
> Description:	Ubuntu 20.04.6 LTS  
> Release:	20.04  
> Codename:	focal



#### 3) The amount of free and used memory


The `-h` option stands for "human-readable" and formats the output in a way that is easy to read by humans, using units like KiB (kibibytes), MiB (mebibytes), GiB (gibibytes), etc.



{% raw %}
```bash
free -h
```
{% endraw %}



![0](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/0.png)



#### **4) GCC Complier**



{% raw %}
```bash
sudo apt install build-essential
gcc --version
```
{% endraw %}



> gcc (Ubuntu 9.4.0-1ubuntu1~20.04.2) 9.4.0  
> Copyright (C) 2019 Free Software Foundation, Inc.  
> This is free software; see the source for copying conditions.  There is NO  
> warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.



## 9. **Mount HDD** 


---



#### 1) Install HDD and listing all part

1. Install Hard Disk on your desktop.
2. Turn on the PC and run command below to check if the install


{% raw %}
```bash
sudo fdisk -l
```
{% endraw %}


1. Identifying one to mount

> Disk /dev/sda: 3.65 TiB, 4000787030016 bytes, 7814037168 sectorsDisk model: ST4000DM004-2U91  
> Units: sectors of 1 * 512 = 512 bytes  
> Sector size (logical/physical): 512 bytes / 4096 bytes  
> I/O size (minimum/optimal): 4096 bytes / 4096 bytes  
> Disklabel type: gpt  
> Disk identifier: 1E186808-864F-4859-BF2A-4A0F5C41347F  
>   
> Device     Start        End    Sectors  Size Type  
> /dev/sda1   2048 7814035455 7814033408  3.7T Linux filesystem

- `/dev/sda` : original HDD address from ‘Disks’ program
- _The size of this disk is 3.6 TiB (4000787030016 bytes)._
- _DOS partition table format cannot be used on drives for volumes larger than 2199023255040 bytes (about 2TB) for 512-byte sectors._
- _We need to use GUID partition table (GPT) format._


#### 2-1) When HDD capacity is over 2TB

1. Type command below on terminal.


{% raw %}
```bash
sudo parted /dev/sda
```
{% endraw %}


1. Type `mklabel` and then type `gpt`
2. A message will be displayed stating that all internal data will be destroyed.
	1. Type `yes` and press Enter to confirm creating the GPT partition table.
3. Type `unit TiB` to change the unit
4. Type `print` to check the capacity
5. Type `mkpart primary 0TiB 3.64TiB` (Change the capacity to yours🙂)
6. Type `q` to quit

![1](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/1.png)



#### 2-2) When HDD capacity is less than 2TB

1. Type command below.


{% raw %}
```bash
sudo fdisk /dev/sda
```
{% endraw %}


1. Follow the instruction below

![2](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/2.png)_https://psychoria.tistory.com/521_



#### 3) Format the partition

1. Type command below


{% raw %}
```bash
sudo mkfs.ext4 /dev/sda
```
{% endraw %}


1. You can ignore the part where you need to enter some informations by pressing ENTER.

![3](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/3.png)_Formatting the partition_



#### 4) Mount

1. Create directory to mount the external hard disk using follwing command.


{% raw %}
```bash
sudo mkdir /mnt/sda
```
{% endraw %}


1. Run the below `mount` command to mount the partition to your mount point directory.


{% raw %}
```bash
sudo mount /dev/sda /mnt/sda
```
{% endraw %}


1. Run the [`df`](https://www.geeksforgeeks.org/df-command-linux-examples/) command below to view all the mounted file systems


{% raw %}
```bash
df -h
```
{% endraw %}



![4](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/4.png)



#### 5) **Configuring Auto-Mounting Partitions**


Add mount information and set the automatic mount for every booting.



{% raw %}
```bash
sudo vi /etc/fstab
```
{% endraw %}


- Add command below at the end.


{% raw %}
```bash
/dev/sda /mnt/sda ext4 defaults 0 0
```
{% endraw %}




#### 6) Creating Symbolic Link for Mount Hard Disk 



{% raw %}
```bash
sudo ln -s /mnt/sda /home/dyan/sda
```
{% endraw %}


- Type `cd  /mnt`  and give a writing and reading authority using `sudo chmod 777 sda`


## 10. Open SSH


---


You can remotely access the PC set as the server from the SSH client of another PC, if you install Open SSH server. Which is much convient development environment.


It was installed in Ubuntu 20.04, but, it is the same in Ubuntu 22.04. 😉



#### 0.Spec


Server PC : Ubuntu 20.04 LTS Desktop


Client PC : MacOS



#### 1. Install **Open SSH Server**


Install Open SSH Server using the following command on terminal.



{% raw %}
```bash
sudo apt update  # update repository
sudo apt install openssh-server
```
{% endraw %}




#### 2. Check ssh execution status



{% raw %}
```bash
sudo systemctl status ssh
```
{% endraw %}



![5](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/5.png)

- If it is not active, run the following commands


{% raw %}
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```
{% endraw %}




#### 3. Activate Firewall


The firewall is disabled by default, and you can check its status with the following command.



{% raw %}
```bash
sudo ufw status
```
{% endraw %}



If the firewall is active, allow ssh. If your firewall is disabled, you can ignore it.



{% raw %}
```bash
sudo ufw allow ssh
```
{% endraw %}




#### 4. Access from Client


Ubuntu has SSH Client installed by default.


If it is not installed, install it with the following command.



{% raw %}
```bash
sudo apt-get install openssh-client
```
{% endraw %}



If SSH Client is installed, you can connect by entering the username and IP address from client PC as follows:



{% raw %}
```bash
ssh {username}@{ip_address}
```
{% endraw %}



![6](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/6.png)


You can check IP address as follows:



{% raw %}
```bash
ip a
```
{% endraw %}



![7](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/7.png)


OR…



{% raw %}
```bash
sudo apt install net-tools
ifconfig
```
{% endraw %}



![8](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/8.png)



#### 5. Deactivate Firewall


You can stop ssh with the following command.



{% raw %}
```bash
 sudo systemctl stop ssh
```
{% endraw %}



You can disable it from running during boot with the following command:



{% raw %}
```bash
sudo systemctl disable ssh
```
{% endraw %}



Conversely, you can enable it to run during launch and boot with the following command:



{% raw %}
```bash
sudo systemctl stop ssh
sudo systemctl enable ssh
```
{% endraw %}




## 11. Install Basics


---



#### **1) Bluetooth**


After updating apt database, We can install `bluetooth` using `apt-get` by running the following command:



{% raw %}
```bash
sudo apt-get -y install bluetooth
sudo systemctl start bluetooth
sudo rfkill unblock bluetooth   # rfkill also requires sudo
sudo reboot
```
{% endraw %}




#### **2) When Hangul doesn’t work**

1. Install and update `ibus` package and `ibus-hangul` package


{% raw %}
```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install ibus ibus-hangul
```
{% endraw %}



![9](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/9.png)

1. Go to **`Settings`** > **`Region & Language`** > Click **`Manage Installed Languages`**

![10](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/10.png)_Go to Settings_


![11](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/11.png)_Go to Region & Language and click Manage Installed Languages._

1. Install the language support when the Language Support window is opened.

![12](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/12.png)_Install the language support._


![13](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/13.png)_Installing and applying changes_

1. Select **`fcitx`** for Keyboard input method system.

![14](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/14.png)_Select fcitx._

1. Click **`+`** button under Input Sources.

![15](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/15.png)_Add new input source._

1. Choose **`Korean(Hangul)`** !!!

![16](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/16.png)

- Set the configurations with ‘Korean(Hangul)’ not ‘Korean’ !!! ⚠️
1. Activate `Hangul mode` from the language setting from the top bar.

![17](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/17.png)_이제 한글 됩니다 😊_

1. Reboot after both installation and system setting.
2. Press `Shift+space` to change the language settings! 🚀

![18](/assets/img/2024-06-24-Development-Environments-[4]:-Ubuntu-20.04-Settings-on-RTX-4080---3.md/18.png)



## 11. Install **Useful programs**


---



#### **1) Useful programs**

- **VSCode, PuTTY, FileZilla, AnyDesk**
- **Microsoft Office, Teams, Outllook, Xpad**


#### **2) KakaoTalk  → don’t**



#### 3) Notion


Open terminal and execute the next commands: 



{% raw %}
```bash
echo "deb [trusted=yes] https://apt.fury.io/notion-repackaged/ /" | sudo tee /etc/apt/sources.list.d/notion-repackaged.list
sudo apt update
sudo apt install notion-app-enhanced
sudo snap install notion-snap-reborn
```
{% endraw %}



OR


[ Install notion-snap-reborn on Ubuntu](https://snapcraft.io/install/notion-snap-reborn/ubuntu)



## References


---

- [https://seongkyun.github.io/others/2019/03/05/hdd_mnt/](https://seongkyun.github.io/others/2019/03/05/hdd_mnt/)
- [https://codechacha.com/ko/ubuntu-install-openssh/](https://codechacha.com/ko/ubuntu-install-openssh/)
- [https://osg.kr/archives/913](https://osg.kr/archives/913)
