---
layout: post
date: 2024-06-25
title: "Development Environments [5]: Ubuntu 20.04 Settings on RTX 4080 - 4"
tags: [settings, Ubuntu 20.04, ]
categories: [Development Environments, ]
---



## Prerequisites


---

- 


## 8. 



#### **Bluetooth**

- Install Blueman in Ubuntu 22.04
- [https://installati.one/install-blueman-ubuntu-22-04/](https://installati.one/install-blueman-ubuntu-22-04/)


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



## 10. Install Notion


---


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

