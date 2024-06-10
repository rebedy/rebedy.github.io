---
layout: post
date: 2024-06-11
title: "Coding Convention [6]"
tags: [coding-convention, linter, ESLint, ]
categories: [Coding Convention, ]
---



## **ESLint 설치하기**



{% raw %}
```text
yarn add -D eslint
```
{% endraw %}



eslint --init으로 기본 config file을 생성해주자.



{% raw %}
```text
yarn eslint --init
```
{% endraw %}



![0](/assets/img/2024-06-11-Coding-Convention-[6].md/0.png)


자신에게 알맞은 옵션들을 설정하면 아래 파일이 자동으로 만들어진다.



{% raw %}
```javascript
// .eslintrc.js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: [
    'airbnb-base',
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaVersion: 12,
    sourceType: 'module',
  },
  plugins: [
    '@typescript-eslint',
  ],
  rules: {
  },
};
```
{% endraw %}



package.json에 scripts 를 추가해주자.



{% raw %}
```javascript
// package.json
...
  "scripts": {
    "lint": "eslint . --fix"
  },
...
```
{% endraw %}




## **Prettier와 통합하기**


Prettier는 단독 CLI 도구가 아닌 일반적으로 ESLint와 같은 린터(Linter)와 통합해서 사용하는 경우가 많다.


Prettier와 ESLint 통합을 위한 2개의 패키지를 설치한다.



{% raw %}
```javascript
yarn add --dev prettier eslint-config-prettier eslint-plugin-prettier
```
{% endraw %}



**.eslintrc.js**에 **extends** 옵션을 추가해준다.



{% raw %}
```javascript
// .eslintrc.js
...
"extends": ["plugin:prettier/recommended"],
...
```
{% endraw %}



기존 설정된 extends 옵션보다 우선하려면 배열 맨 뒤에 추가하면 된다.

