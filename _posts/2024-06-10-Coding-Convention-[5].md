---
layout: post
date: 2024-06-10
title: "Coding Convention [5]"
tags: [coding-convention, linter, ]
categories: [Coding Convention, ]
---



## 0. Prerequsites


---


**[1]** [**Coding-Convention-1-Code-Formatter**](https://rebedy.github.io/posts/Coding-Convention-1-Code-Formatter/)


**[2]** [**Coding-Convention-2-Black**](https://rebedy.github.io/posts/Coding-Convention-2-Black/)


**[3]** [**Coding-Convention-3-Prettier**](https://rebedy.github.io/posts/Coding-Convention-3-Prettier/)


**[4]** [**Coding-Convention-4-autopep8**](https://rebedy.github.io/posts/Coding-Convention-4-autopep8/)



## 1. Linter?


---


![0](/assets/img/2024-06-10-Coding-Convention-[5].md/0.png)


![1](/assets/img/2024-06-10-Coding-Convention-[5].md/1.png)_https://velog.io/@adbr/flutter-flutter-linter-package-effectivedart_


It's a small program that checks coding conventions and errors. It can be run independently or as a plugin in an IDE.


Because it supports most syntax including Python, Ruby, Java, Swift, HTML, CSS, YAML, and even Markdown, you can immediately check any programming language you use.


It is a tool for flagging program errors, bugs, style errors, and suspicious structures by analyzing the source code. It refers to a static type analysis tool.


Identifying and marking parts of the code that do not follow the style rules set by the community or team.


The origin of the linter was originally a tool called `lint` that analyzed C source code, and not only `lint` but also several `utilities` at this time analyzed the source code for compiler optimization. However, currently, `linters` are widely used not only for compilers but also for improving the source code itself.



### 1) [Static program analysis](https://en.wikipedia.org/wiki/Static_program_analysis)


Linters are ultimately part of static analysis.


It's a `pre-run debug`. A method of analyzing code without running the program.


Through this, potential problems such as errors and convention adherence can be found.



### 2) Pros

- Can reduce errors.
- Readability + Good for maintenance.
- Can reduce issues about code style during review.
- Enables objective code quality measurement.


### 3) What do Linters provide?

- Syntax Errors
- **Code standards adherence**
- Potential problems (a.k.a code smells)
- Security checks


### 4) Differences between Code Formatter



#### **4-1. Formatter**

- Modifies code style (examples: spacing, line breaks, comments, etc.). It has a feature to sort according to the rules established for the written code.


#### **4-2. Linter**

- It analyzes the code to find errors and provides best practices for better code quality.


#### 4-3. The most ideal use case

1. Modify (or unify) the code style with the **Formatter**
2. Use **Linter** to correct potential errors or use better syntax.
- Using the **Linter and Formatter together** automatically organizes the code each time you save, making it easy to identify any incorrectly written code.


## 2. Types of Linter


---



### 1) Python


![2](/assets/img/2024-06-10-Coding-Convention-[5].md/2.png)


|              | **flake8**                            | **pylint**                                 | **bandit**          |
| ------------ | ------------------------------------- | ------------------------------------------ | ------------------- |
| **Types**    | linter                                | linter                                     | security linter     |
| **Stars**    | 2.3K                                  | 4.2K                                       | 4.5K                |
| **Features** | Check code style and error complexity | Check code style, code smells, and errors  | Check unsafe coding |
| **Pros**     | Simple, lots of plugins               | Setting cost is higher than flake8         |                     |
| Cons         | Has many plugins                      | Passing Lint is more difficult than flake8 |                     |

undefined- It can be used mixed.


#### **1-1. flake8**


Checks code conventions based on Python's leading lint tool, PEP8. It checks code style, errors, and complexity and wraps the package below.


**A Python linting library** that basically wraps three other linters, PyFlakes, pycodestyle and Ned Batchelder's McCabe Script.

- `pycodestyle` : PEP8 compliance check (Error code : E**/ W*** / N8**)
- `pyflakes` : Errors, violations of common practices, etc. (Error code : F***)
- `McCabe complexity checker` : (Error code : C9***)

**1-1-1. Installation and usage**



{% raw %}
```bash
# Install Flake8
$ python -m pip install flake8


# Using Flake8
$ flake8 path/to/code/to/check.py
# or
$ flake8 path/to/code/
```
{% endraw %}



[**1-1-2. With the** ](https://flake8.pycqa.org/en/latest/user/using-hooks.html)[**`pre-commit`**](https://flake8.pycqa.org/en/latest/user/using-hooks.html)[ **git hooks**](https://flake8.pycqa.org/en/latest/user/using-hooks.html)


Add code below to `.pre-commit-config.yaml`



{% raw %}
```yaml
-repo: https://github.com/pycqa/flake8
rev: ''# pick a git hash / tag to point tohooks:
    -id: flake8
```
{% endraw %}



**1-1-3. Links**

- [**Github**](https://github.com/PyCQA/flake8)
- [**Docs**](https://flake8.pycqa.org/en/latest/)


#### 1-2. pylint


Check for code style, code smell, type errors, etc. (Need to install a plugin for complexity)


It's harder to pass lint than flake8.


There are a lot of settings. You can set the rules.


A lint rating comes out after the final inspection.


[**1-2-1. Pre-commit integration**](https://pylint.pycqa.org/en/latest/user_guide/installation/pre-commit-integration.html#pre-commit-integration)


Add to `.pre-commit-config.yaml` as follows:



{% raw %}
```yaml
- repo: local
  hooks:
    - id: pylint
      name: pylint
      entry: pylint
      language: system
      types: [python]
      require_serial: true
      args:
        [
          "-rn", # Only display messages
          "-sn", # Don't display the score
        ]
```
{% endraw %}


- [**using Black & Pylint & Pre-commit as Git Hooks**](https://towardsdatascience.com/keep-your-code-clean-using-black-pylint-git-hooks-pre-commit-baf6991f7376)

**1-2-2. Links**

- [**Github**](https://github.com/PyCQA/pylint)
- [**Docs**](https://pylint.pycqa.org/en/latest/index.html)


#### 1-3. bandit (security linter)


Checking unsafe coding (exec, assert debug=True), etc. AWS has services such as bandit-based security detection. Rather than analyzing code style, it identifies security issues in the code. Detect unsafe code.


**1-3-1. Prerequisites**


Python, Flask, SQLAlchemy, and Bandit.



{% raw %}
```bash
pip install bandit
pip install flask
pip install flask-sqlalchemy
```
{% endraw %}



**1-3-2. Using Bandit**



{% raw %}
```bash
bandit example.py
```
{% endraw %}



**1-3-3. Links**

- [**Github**](https://github.com/PyCQA/bandit)
- [**Docs**](https://bandit.readthedocs.io/en/latest/)


### 2) Javascript



#### 2-1. JSLint


Javascript static analysis tool created by Douglas Crockford. Because the rule is too strict, JSHint, which slightly relaxes this rule, is used more.


**2-1-1. Links**

- [**Website**](https://www.jslint.com/)
- [**Github**](https://github.com/jslint-org/jslint)


#### 2-2. JSHint


A Javascript static analysis tool derived from the above-mentioned JSLint and created by Anton Kovalyov by forking JSLint in 2011. Community-based tool to detect errors and potential problems in JavaScript code. It has the advantage of being able to turn most options on and off.


**2-2-1. Links**

- [**Website**](https://jshint.com/)
- [**Docs**](https://jshint.com/docs/)
- [**Github**](https://github.com/jshint/jshint)


#### 2-3. JSCS


It is a code style linter created by Marat Dulin in 2014. You can import and use code style preset tools from various projects/companies/teams such as Google, Airbnb, and jQuery, or customize the style.


While JSLint and JSHint focus on providing best coding practices, <u>JSCS only specifies the coding style and does not provide a way to check and modify the coding style.</u> It serves as a programmatic coding style guide.


**2-3-1. Links**

- [**Website**](https://jscs-dev.github.io/)
- [**Github**](https://github.com/jscs-dev/node-jscs)


#### 2-4. ESLint


Javascript static analysis tool created by Nicholas C. Zakas in 2013.


Because both SLint and JSHint lacked the ability to create additional rules for code quality and coding style, we created ESLint, a new linting tool that allows you to configure all rules and define or load additional rules at runtime. It is a pluggable JavaScript linter that provides both the functions provided by JSHint and the code style check function provided by JSCS.


ESLint allows users to select the desired support environment. Basically, it supports ECMAScript5 grammar.


You can change the options to create an environment that supports ECMAScript6 or JSX.


**2-4-1. Links**

- [**Website**](https://eslint.org/)
- [**DEMO**](https://eslint.org/demo)
- [**Github**](https://github.com/eslint/eslint)


### 3) Swift



#### 3-1. SwiftLintCore


A tool to enforce Swift style and conventions. It ensures that all Swift code remains consistent. 


**3-1-1. Rules**


Currently, SwiftLint has over 75 rules. There are three main parameters that set whether to apply a rule.

1. **disabled_rules**: Specifies rules to be disabled among the default activated rules.
2. **opt_in_rules**: Activates rules other than the default rules.
3. **whitelist_rules**: Specifies a whitelist so that only the specified rules are activated. <u>Cannot be used with</u> <u>_disabled_rules_</u> <u>and</u> <u>_opt_in_rules_</u><u>.</u>

**3-1-2. Links**

- [**Website**](https://realm.github.io/SwiftLint/index.html)
- [**Rules**](https://realm.github.io/SwiftLint/rule-directory.html)
- [**GitHub**](https://github.com/github/swift-style-guide)
