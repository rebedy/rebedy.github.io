---
layout: post
date: 2024-06-07
title: "Coding Convention [2]: Black"
tags: [coding-convention, code-formatter, black, ]
categories: [Coding Convention, ]
---



## Prerequisites


---


**[1]** [**Coding-Convention-1-Code-Formatter**](https://rebedy.github.io/posts/Coding-Convention-1-Code-Formatter/)



## [Black](https://black.readthedocs.io/en/stable/)


---


Code formatting tool that unifies code style


[black-github](https://github.com/psf/black)


![0](/assets/img/2024-06-07-Coding-Convention-[2]:-Black.md/0.png)



## Installation


---



{% raw %}
```bash
pip install black
```
{% endraw %}




### With Command-line



#### Check if Formatting to edit 



{% raw %}
```bash
black --check [file_name or folder_name]
```
{% endraw %}




#### Editing Formatting



{% raw %}
```bash
black [file_name or folder_name]
```
{% endraw %}




### With VSCode



#### Designate to Formatter in VSCode

- Add to VSCode preferences to run Black as default formatter
	- Go to `.vscode/setting.json` in the command palette(`ctrl+shift+P`).
	- Add commands below.


{% raw %}
```json
"python.formatting.provider": "black“,  # Allows VSCode to use Black instead of its default formatter.
"editor.formatOnSave": true,  # Automatically format the code every time you save it.
```
{% endraw %}




## Options


---

- `l` : Maximum number of characters per line (initial value 88)
- `—diff` : Shows the changed parts in the console without changing the file.
- `—color` : Colors the changes when using `—diff`.
- You can preview changes with `black {파일명 또는 폴더명} -l 80 --diff --color.`


## **Git hook Setting**


---

- Since code editor settings are ultimately a personal choice, it is advisable to avoid attempting to commit unformatted code at the project level.


#### 1. Install `pre-commit` package 



{% raw %}
```bash
pip install pre-commit
```
{% endraw %}




#### 2. Generate `.pre-commit-config.yaml` file



#### 3. Add



{% raw %}
```yaml
repos:
  - repo: https://github.com/psf/black
    rev: stable
    hooks:
      - id: black
```
{% endraw %}




#### 4. `pre-commit` 

- Install the Git hook script you just wrote above.


{% raw %}
```bash
$ pre-commit install
pre-commit installed at .git/hooks/pre-commit
```
{% endraw %}




#### 5. Try to commit after disabling the code editor's automatic formatting.



#### 6. The Git hook script runs, the commit fails, and Black does the formatting.



## How to avoid formatting


---


 **# fmt : off / on / skip**


Code Formatter is usually specified to run automatically when saving a file or creating a commit. However, there are times when you do not want Code Formatter to run. In that case, set as below.



{% raw %}
```bash
# fmt: off
--- codes excluded from formatting ---
# fmt: on
```
{% endraw %}



If you want to avoid formatting only a specific line within the code, you can use `# fmt: skip` at the end of that line.



## References


---

- [https://www.daleseo.com/python-black/](https://www.daleseo.com/python-black/)
- [https://www.daleseo.com/pre-commit/](https://www.daleseo.com/pre-commit/)
