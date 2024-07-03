---
layout: post
date: 2024-06-07
title: "Coding Convention [2]: Black"
tags: [coding-convention, code-formatter, black, ]
categories: [Coding Convention, ]
math: false
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



#### Install the extension


Extensions (**`^+⌘+X`**) > Type ‘**Black Formatter**’ > Install 



#### Designate to Formatter in VSCode

- Add to VSCode preferences to run Black as default formatter
	- Go to `.vscode/setting.json` in the command palette(**`⌘+shift+P`**).
	- Add commands below.


{% raw %}
```json
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter"
  }
```
{% endraw %}




#### **Format on save**


Automatically format your Python files on save by setting the `editor.formatOnSave` setting to `true` and the `editor.defaultFormatter` setting to `ms-python.black-formatter`. You can also enable format on save for Python files only by adding the following to your settings:



{% raw %}
```json
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.formatOnSave": true
  }
```
{% endraw %}




#### Settings


**1.** **`black-formatter.args`**

- Default: []
- Description
	- Passing arguments to Black to specify the Python file format. string.
	- e.g. "black-formatter.args" = ["--config", "<file>"]

**2.** **`black-formatter.cwd`**

- Default: []
- Description
	- Sets the current working directory used to format Python files to Black.
	- By default, the root directory of the workspace `${workspaceFolder}` is used.
	- If set to `${fileDirname}`, the parent folder can be used as the working directory.

**3.** **`black-formatter.path`**

- Default: []
- Description
	- Path or command to be used by the extension.
	- Array of single or multiple strings.
	- Each argument is provided as a separate string in the array.
	- Setting to ["black"] will use the Black version available in the PATH environment variable. This may slow formatting.
	- e.g. ["~/global_env/black"]["conda", "run", "-n", "lint_env", "python", "-m", "black" ]

**4.** **`black-formatter.interpreter`** 

- Default: []
- Description
	- Path to the Python executable or command used to start the Black server and child processes.
	- Allows arrays of single or multiple strings.
	- Each argument is provided as a separate string in the array.
	- If set to `[]`, the path to the selected Python interpreter will be used.

**5.** **`black-formatter.importStrategy`** 

- Default: useBundled
- Description
	- Defines the Black formatter binary.
	- If set to `useBundled`, the included Black Formatter binary will be used.
	- When set to `fromEnvironment`, attempts to use the Black Formatter binary and all dependencies available in the currently selected environment.
	- **Note**: If the extension cannot find a valid Black Formatter binary for the selected environment, it will fallback to using the accompanying binary.
	- The `black-formatter.path` setting takes precedence over the action of `black-formatter.importStrategy`.

**6.** **`black-formatter.showNotification`**

- Default: off
- Description
	- Controls when notifications are shown by this extension.
	- e.g. `onError`, `onWarning`, `always` and `off`

**7.** **`black-formatter.serverTransport`**

- Default: stdio
- Description
	- Selects the transport protocol to be used by the Black server.
	- When set to `stdio`, the extension will use the standard i/o streams.
	- When set to `pipe`, the extension will use a named pipe (on Windows) or Unix Domain Socket (on Linux/Mac).
	- The `stdio` transport protocol is the default and recommended option for most users.


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
