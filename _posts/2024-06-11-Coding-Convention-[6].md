---
layout: post
date: 2024-06-11
title: "Coding Convention [6]"
tags: [coding-convention, linter, ESLint, javascript, ]
categories: [Coding Convention, ]
---



## Prerequisites


---


**[1]** [**Coding-Convention-1-Code-Formatter**](https://rebedy.github.io/posts/Coding-Convention-1-Code-Formatter/)


**[2]** [**Coding-Convention-2-Black**](https://rebedy.github.io/posts/Coding-Convention-2-Black/)


**[3]** [**Coding-Convention-3-Prettier**](https://rebedy.github.io/posts/Coding-Convention-3-Prettier/)


**[4]** [**Coding-Convention-4-autopep8**](https://rebedy.github.io/posts/Coding-Convention-4-autopep8/)


**[5]** [**Coding-Convention-5-Linter**](https://rebedy.github.io/posts/Coding-Convention-5-Linter/)



## ESLint


---


![0](/assets/img/2024-06-11-Coding-Convention-[6].md/0.png)


Javascript static analysis tool created by Nicholas C. Zakas in 2013.


**ES(EcmaScript) + Lint.** ESLint was created since both JSLint and JSHint lacked the ability to create additional rules for code quality and coding style. ESLint is a linting tool that allows you to configure all rules and define or load additional rules at runtime. It is a pluggable JavaScript linter that includes both the functionality provided by JSHint and the code style checking features provided by JSCS. A variety of plugins are available, allowing you to add new rules and easily introduce settings from other companies or people.



## **Getting Started with ESLint**


---



### **1. Installing Yarn on macOS**



#### Using Homebrew



{% raw %}
```bash
brew install yarn
```
{% endraw %}




#### **Using Shell Script**



{% raw %}
```bash
curl -o- -L https://yarnpkg.com/install.sh | bash
```
{% endraw %}




### 2. Installing ESLint



{% raw %}
```bash
yarn add -D eslint
```
{% endraw %}



![1](/assets/img/2024-06-11-Coding-Convention-[6].md/1.png)



#### Generate basic config file



{% raw %}
```bash
yarn eslint --init
# or
npm init @eslint/config@latest
```
{% endraw %}



![2](/assets/img/2024-06-11-Coding-Convention-[6].md/2.png)


The file below will be generated with the options you set.



{% raw %}
```javascript
// eslint.config.js
export default [
    {
        rules: {
            "no-unused-vars": "error",
            "no-undef": "error"
        }
    }
];
```
{% endraw %}




### 3. Run ESLint on any file or directory



{% raw %}
```bash
npx eslint example.js

# or

yarn run eslint example.js
```
{% endraw %}




## **Integrate with** [**Prettier**](https://rebedy.github.io/posts/Coding-Convention-3-Prettier/)


---


[**Prettier**](https://rebedy.github.io/posts/Coding-Convention-3-Prettier/) is not a standalone CLI tool. It is often used integrated with a linter such as ESLint.


Install two packages for **Prettier and ESLint integration**.



{% raw %}
```bash
yarn add --dev prettier eslint-config-prettier eslint-plugin-prettier
```
{% endraw %}



Add `extends` option in **`.eslintrc.js`**



{% raw %}
```javascript
// .eslintrc.js
...
"extends": ["plugin:prettier/recommended"],
...
```
{% endraw %}



To take precedence over the existing extends option, add it to the end of the array.

