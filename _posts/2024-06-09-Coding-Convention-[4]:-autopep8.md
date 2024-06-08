---
layout: post
date: 2024-06-09
title: "Coding Convention [4]: autopep8"
tags: [coding-convention, code-formatter, autopep8, PEP8, ]
categories: [Coding Convention, ]
---



## [**autopep8**](https://pypi.org/project/autopep8/)


---


![0](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/0.png)_https://all-share-source-code.tistory.com/80_


Module that automatically corrects Python code to conform to the **PEP8 convention**.

	- **PEP8** is the official Python style guide.


### 1. Install and set autopep8

- **Installation**
	- **Extension > Search** **`autopep8`** **> Install** **`autopep8`** **extension**
- **Setting**
	- **Settings (** **`ctrl + ,`****) > Search** **`python formatting`** **> Find** **`Python > Formatting: Provider`** **> Set to** **`autopep8`**


### 2. When installation does not work / is not in the options


If **autopep8** does not appear in the python formatting options, you need to change the settings.


When other python code formatter (**Prettier**) is already set as the default so it cannot be set as **`autopep8`**.


![1](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/1.png)



#### 2-1. Change setting in `settings.json`


The formatter can only be changed in python format files this way.

- Settings (**`Ctrl + Shift + P`****)** > Enter **`open user settings`** > Go to **`Preferences: Open User Settings (JSON)`** > Add code below in between the braces > Save > Restart VSCode


{% raw %}
```json
{
...
    "[python]": {
      "editor.formatOnType": true,
      "editor.defaultFormatter": "ms-python.autopep8",
      "editor.formatOnSave": true
    },
...
}
```
{% endraw %}




#### 2-2. Change default formatter


We gotta be careful with this one. ⚠️ The formatter is applied as **autopep8** in all files. So if you are working on the other developments simultaneously, the formatting method may be messed up! If you are working on python ONLY then this will be fine. 🙂

- Settings > Search **`Default Formatter`** > Choose **`autopep8`**


### 3. Set to automatically run on the save


Once it’s activated, the formatter will run automatically when the file is saved. If not set, you must run the formatter manually.

- **Settings (** **`ctrl + ,`****) > Search** **`format on save`**  **> Activate > Restart VSCode**

![2](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/2.png)



## [PEP8](https://peps.python.org/pep-0008/)


---


Code conventions differ across programming languages. For Python, the convention is known as **PEP8**.


The **autopep8** package offers automatic formatting. However, it's not flawless, so it's beneficial to familiarize yourself with it before use.



### 1. Naming Convention


| **Types**    | **Naming Convention**                                                                                                                                           | **example**                                     |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| **Function** | Use a **lowercase** word/words. Use underscores to separate works for readability.                                                                              | function, my_function                           |
| **Variable** | Use a **lowercase** single letter, word/words. Use underscores to separate works for readability.                                                               | x, var, my_variable                             |
| **Class**    | Use [**camel case or Pascal case**](https://en.wikipedia.org/wiki/Camel_case). Start each word with a capital letter and don’t separate words with underscores. | Model, MyClass                                  |
| Method       | Use a lowercase word/words. Separate words with underscores to improve readability.                                                                             | class_metho                                     |
| **Constant** | Use an **uppercase** single letter, word/words. Use underscores to separate works for readability.                                                              | CONSTANT, PYTHON_CONSTANT, PYTHON_LONG_CONSTANT |
| **Module**   | Use a **short**, **lowercase** word/words. Use underscores to separate works for readability.                                                                   | module.py, my_module.py                         |
| **Package**  | Use a **short**, **lowercase** word/words. Don’t separate words with underscores.                                                                               | package, mypackage                              |

undefined

### 2. **Code Layout**



## References


---

- [https://hangbok-archive.com/development/devkit/autopep8-설치/](https://hangbok-archive.com/development/devkit/autopep8-%EC%84%A4%EC%B9%98/)
- [https://realpython.com/python-pep8/](https://realpython.com/python-pep8/)
