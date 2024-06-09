---
layout: post
date: 2024-06-08
title: "Coding Convention [3]: Prettier"
tags: [coding-convention, code-formatter, prettier, ]
categories: [Coding Convention, ]
---



## Prerequsites


---


**[1]** [**Coding-Convention-1-Code-Formatter**](https://rebedy.github.io/posts/Coding-Convention-1-Code-Formatter/)


**[2]** [**Coding-Convention-2-Black**](https://rebedy.github.io/posts/Coding-Convention-2-Black/)



## Prettier


---


![0](/assets/img/2024-06-08-Coding-Convention-[3]:-Prettier.md/0.png)


Prettier is a code formatter and a VSCode Extension.


Prettier is a **JavaScript library** that has become the most popular among code formatters and is almost becoming a standard.


Open source projects and many companies are using Prettier as their official code formatter. (Facebook, React, Jest, Yarn, Babel, Webpack, Dropbox, Storybook, Paypal, MongoDB, Salesforce, …)


The reason why Prettier has quickly become popular is that, unlike other existing code formatters, there is little room for configuration. In other words, it is difficult to significantly deviate from the default coding style in Prettier. == Ease to set!


This means that once you start using Prettier, you don’t need to argue with your team members about coding style!😉



## **Install Prettier Library**


---


The **Prettier** library is uploaded to the npm public repository as a package named `prettier`.


Therefore, it can be easily installed and used in any JavaScript project through npm package manager.


Since **Prettier** is not needed for an application execution, we can install it as a development dependency using the `-D` option.



{% raw %}
```bash
$ npm i -D prettier
```
{% endraw %}




## Prettier Setting


---

1. Install **IntelliJ IDE Plugins**.
	1. **Settings(****`Ctrl + Alt + s`****) > plugins > Search** **`Prettier`** **> Install > IDE restart**
	2. **Extensions > Search** **`Pretter`** **> Install**


## Specifying the coding style


---

1. **Settings(****`Ctrl + Alt + s`****) > search** **`Prettier`** **> configuration**
2. Manage with **`.prettierrc.json`** **or** **`.prettierrc.js`** or etc. (Prettier configuration file)
3. File examples


{% raw %}
```json

// .prettierrc.json
{
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": false,
  "bracketSpacing": true,
  "printWidth": 80
}


// prettier.config.js or .prettierrc.js
module.exports = {
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": false,
  "bracketSpacing": true,
  "printWidth": 80
}
```
{% endraw %}


1. Setting for configuration path
	1. **Config Path >** **`.prettierrc.json`**


## Setting for automatic sorting on save


---


Set the **`Default Formatter`** to **Prettier** and then check the **`Format on Save`** setting.


![1](/assets/img/2024-06-08-Coding-Convention-[3]:-Prettier.md/1.png)


> 👸 _**If the settings don't work, try turning it off and then back on!**_

