---
layout: post
date: 2025-01-28
title: "Development Environments [2]: Ubuntu 20.04 Settings on RTX 4080 -4 - "
tags: [settings, Ubuntu 20.04, d2codingfont, terminator, ]
categories: [Development Environments, ]
math: false
---



## [D2Coding](https://github.com/naver/d2codingfont) Font


---


![0](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/0.png)_D2CodingFont_


D2 Coding font was created for developers and coding based on Nanum Barun Gothic. It is a font optimized for readability, differentiation between similar characters, and harmony with Korean in terms of design. D2 Coding font has enhanced differentiation and readability for not only similar English letters and numbers, but also Korean and special characters when coding. It is also designed to maintain the spacing between letters and lines in any development environment as it is a fixed-width font.

- version I downloaded: [**D2Coding Ver 1.3.2**](https://github.com/naver/d2codingfont/releases/tag/VER1.3.2)


### 1) Download D2Coding Font

1. Download `D2Coding font` zip file to current directory.


{% raw %}
```bash
wget <https://github.com/naver/d2codingfont/releases/download/VER1.3.2/D2Coding-Ver1.3.2-20180524.zip>
```
{% endraw %}


1. Unzip the downloaded file to `/usr/share/fonts/d2coding`.


{% raw %}
```bash
sudo unzip -d /usr/share/fonts/d2coding D2Coding-Ver1.3.2-20180524.zip
```
{% endraw %}


1. 내려받은 zip 파일을 삭제해준다.


{% raw %}
```bash
rm D2Coding-Ver1.3.2-20180524.zip
```
{% endraw %}




### 2) Install FontConfig



{% raw %}
```bash
sudo apt install fontconfig
sudo fc-cache -f -v
fc-list | grep -i d2c
```
{% endraw %}




### 3) Set On the Terminal

1. First, let’s go to `Preferences` from the `≡` button.

![1](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/1.png)_Let’s go to Preferences!_

1. Then go to `Profiles` > `Choose A Terminal Font`

![2](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/2.png)_Setting up to D2Coing Bold_

1. You can check the changed font right away!

![3](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/3.png)_D2 Coding Font Installed!_



## Terminator


---


![4](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/4.png)_Terminator_



### What is [`Terminator`](https://terminator-gtk3.readthedocs.io/en/latest/)?


It is a terminal emulator like xterm, gnome-terminal, konsole, etc. It also is an open source terminal emulator written in **Java**. `Terminator` can be used on Windows, MacOS, Linux, and other Unix systems.


I usually use iTerm2 on my MacBook, but for the server desktop I installed `Terminator` since the Ubuntu default terminal, which is good, but has no the spliting window and other functions.



### 1) Install the Terminator


Type the commands below one by one in order to install the `Terminator`.



{% raw %}
```bash
sudo apt update
sudo apt install terminator
```
{% endraw %}



![5](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/5.png)_This is what it looks like for the installation!👩‍💻_



### 2) Set the Terminator


You can find the `Terminator` through search.


![6](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/6.png)_Search for Terminator!_


This is what it looks like when you open the `terminator`!


![7](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/7.png)_This is how it looks!_



### 3) Set the Font Globally

1. Check out: Right click > `Preferences` > `Keybindings`
2. Uncheck ‘Use the system font’ and click box on the right side of ‘Font:’.

![8](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/8.png)_Clike the Sans Regular 9 button._

1. Set the font to `D2Coding Bold`

![9](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/9.png)_Let’s set the font to D2Coing Bold!_



### 4) Set the Font from the Profile

- Check out: Right click > `Preferences` > `Profiles` > `Font:`
- Then set it to the `D2Coding Bold`.
- This will set the font as a default since you use the default profile.

![10](/assets/img/2025-01-28-Development-Environments-[2]:-Ubuntu-20.04-Settings-on-RTX-4080--4---.md/10.png)



### 5) Set the config file


We also can change configs in `.config/terminator/config` file.



{% raw %}
```bash
vi ~/.config/terminator/config
```
{% endraw %}




### 6) Shortcuts


There are many shortcuts! I have selected a few that can be used frequently which is good to know. 😉

- Vertical Split: **`Ctrl`** **+** **`Shift`** **+** **`E`**
- Horizontal Split: **`Ctrl`** **+** **`Shift`** **+** **`O`**
- Close current window: **`Ctrl`** **+** **`Shift`** **+** **`W`**
- Move between terminal window: **`Alt`** **+ Arrow Keys**
- Resize terminal window: **`Ctrl`** **+** **`Shift`** **+ Arrow Keys**
- Switch between tabs: **`Ctrl`** **+** **`Page Up`** **/** **`Page Down`**
- 


## References


---

- [https://m-hangeul.naver.com/font/detail/nanum-gothic-coding](https://m-hangeul.naver.com/font/detail/nanum-gothic-coding)
- [https://github.com/naver/d2codingfont](https://github.com/naver/d2codingfont)
- [https://gnome-terminator.org/](https://gnome-terminator.org/)
- [https://2dudwns.tistory.com/7](https://2dudwns.tistory.com/7)
