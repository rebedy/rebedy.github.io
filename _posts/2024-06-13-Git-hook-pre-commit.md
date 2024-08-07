---
layout: post
date: 2024-06-13
title: "Git hook pre-commit"
tags: [coding-convention, linter, git-hook, pre-commit, black, flake8, ]
categories: [GitHub, ]
math: false
---



## `pre-commit` hook of Git


---


![0](/assets/img/2024-06-13-Git-hook-pre-commit.md/0.png)


A **Git hook** is a function in Git that executes a specific script at an event. **Git** **`pre-commit`** **hook** automatically executes certain tasks every time we commit our code. So basically it is called before we actually write a commit message. We can automate code checking before commit with `pre-commit`. This can be used to check for grammar errors, style, alignment, and type errors before committing. Many projects use this to run a <u>Code Formatter</u> to unify the code style and run a <u>Linter</u> to find potential problems in the code. It can even be customized according to the developer’s preference. And also the biggest advantage of `pre-commit` is that just as Git is language-agnostic, this can be used regardless of programming language.



## Getting started with `pre-commit`


---



#### 1. Initialize git



{% raw %}
```bash
git init
```
{% endraw %}




#### 2-1. When `python` is installed.


When there is Python installed already then you can just use `pip`.



{% raw %}
```bash
pip install pre-commit
pre-commit -V
```
{% endraw %}



![1](/assets/img/2024-06-13-Git-hook-pre-commit.md/1.png)



#### 2-2. On MacOS


If Python is not installed, you can also install it through package manager from your operating system. MacOS users can use `homebrew`.



{% raw %}
```bash
brew install pre-commit
pre-commit -V
```
{% endraw %}




#### 3. Config setting


`pre-commit` needs it’s own config file. We can create a configuration file using a command that outputs sample settings to the terminal.



{% raw %}
```bash
pre-commit sample-config > .pre-commit-config.yaml
cat .pre-commit-config.yaml
```
{% endraw %}



We can check out that **four hooks** have been set.


![2](/assets/img/2024-06-13-Git-hook-pre-commit.md/2.png)


The `pre-commit` tool downloads and executes hooks from Git repositories. So, we need to know which Git repository the hook is located in. You can see various pre-commit hooks on the [**Supported hooks**](https://pre-commit.com/hooks.html) page on the `pre-commit` official website.


**Another example of** **`.pre-commit-config.yaml`** **file**



{% raw %}
```yaml
repos:
  - repo: https://github.com/ambv/black
    rev: ''  # you also can set the version for repo
    hooks:
      - id: black
        language_version: python3.8  # please change the python version
  - repo: https://gitlab.com/pycqa/flake8
    rev: ''
    hooks:
      - id: flake8
  - repo: https://github.com/pycqa/isort
    rev: ''
    hooks:
      - id: isort
  - repo: https://github.com/necaris/pre-commit-pyright
    rev: ''
    hooks:
      - id: pyright
```
{% endraw %}



You can update `rev` version automatically by `pre-commit autoupdate`.



#### 4. Add and run



{% raw %}
```bash
git add .pre-commit-config.yaml
pre-commit run -a
```
{% endraw %}




#### 5. Git commit



{% raw %}
```bash
git commit -m "creates .pre-commit-config.yaml"
```
{% endraw %}




#### 6. Test


To check whether it is set properly, let’s try intentionally adding a trailing-whitespace.
If you stage the created file by `add` and run the `pre-commit`, the trailing-whitespace hook will fail.



{% raw %}
```bash
echo "Testing trailing whitespace.   " > text.txt
git add test.txt
pre-commit run
```
{% endraw %}



But you don't have to worry!😺 Files where hooks fail will be automatically modified, so if you stage the changes and run `pre-commit` again, then all hooks will pass!



{% raw %}
```bash
git status. # check the changes
git add test.txt
pre-commit run
```
{% endraw %}




#### 7. Automation


The ultimate purpose of using `pre-commit` is **to automatically execute a specific task** every time a commit is made, so all developers in the project must run the `pre-commit`.


With the command below, pre-commit will be automatically executed every time you try to commit, without running it manually.



{% raw %}
```bash
pre-commit install
```
{% endraw %}




## References


---

- [https://www.daleseo.com/pre-commit/](https://www.daleseo.com/pre-commit/)
