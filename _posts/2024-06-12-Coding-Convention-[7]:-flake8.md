---
layout: post
date: 2024-06-12
title: "Coding Convention [7]: flake8"
tags: [coding-convention, code-formatter, linter, flake8, Python, ]
categories: [Coding Convention, ]
---



## [`flake8`](https://pypi.org/project/flake8/)


---


![0](/assets/img/2024-06-12-Coding-Convention-[7]:-flake8.md/0.png)_https://dev.to/bowmanjd/some-flake8-plugins-for-python-linting-107h_


`flake8` is **a command-line utility for enforcing style consistency across Python projects**.


It is a Python code [**linter**](https://rebedy.github.io/posts/Coding-Convention-5-Linter/) tool that checks for errors, styling issue and complexity. It is the wrapper which verifies pep8, pyflakes, and circular complexity. The Flake8 library is built upon 3 tools:

- **pycodestyle** - checks your Python codebase for styling issues against PEP8.
- **PyFlakes** - checks your Python codebase for errors
- **McCabe** - checks your Python codebase for complexity

It has a low rate of false positives.



## Getting start with `flake8`


---



### 1. Install



{% raw %}
```bash
pip install flake8
# or
python -m pip install flake8
```
{% endraw %}




### 2. Run



{% raw %}
```bash
flake8 {path_to_code}# check the whole repository
flake8 example.py # check for particular file
```
{% endraw %}




### 3. Inclusion and exclusion


You also have the option to select specific errors or warnings to focus on, allowing you to filter and view only the instances of a particular warning or error, which can help streamline the debugging process and make it easier to identify and address specific issues.



{% raw %}
```bash
flake8 --select E123,W503 {path_to_code}
```
{% endraw %}



Alternatively, if you prefer to exclude certain warnings or errors from your view, you can add specific warnings or errors to an ignore list. This enables you to streamline the information presented to you and focus solely on the messages that are relevant to your current task.



{% raw %}
```bash
flake8 --extend-ignore E203,W234 {path_to_code}
```
{% endraw %}



\You can simply let the shell in your terminal automatically locate Flake8. However, if you have installed Flake8 for multiple versions of Python (e.g., Python 3.8 and Python 3.9) and need to call a specific version, you'll get better results by specifying the version you want to use. In such cases, you can use a command like this to ensure the correct version of Flake8 is invoked:



{% raw %}
```bash
python<version> -m pip install flake8
```
{% endraw %}



Or you also can choose what to include or exclude from configuration file. By creating a `.flake8` file and entering the following information, you can exclude folders and files to be excluded and also set error messages to be ignored.



{% raw %}
```text
[flake8]
exclude =
    .git,
    .gitignore,
    *.pot,
    *.py[co],
    __pycache__,
    venv,
    .env

ignore =
        E128, E203, E501, W234, W291
```
{% endraw %}



Create a configuration file in the path below, if you want to set the configuration file globally.



{% raw %}
```bash
# Linux, OS X
~/.config/flake8

# Windows
~\.flake8
```
{% endraw %}




## Using with VSCode


---


Assuming you have installed flake8, you can use flake8 in VSCode by following the steps below.



#### Python: Select Linter

- **Command Palette** **`⌘+shift+P`** > Type and select  ”Python: Select Linter” > Type and select “flake8” > Type  and select “Python: Run Linting” will activate linting


#### Configuration

- **Command Palette** **`⌘+shift+P`**  > Select “setting.json” > `.vscode/setting.json`


{% raw %}
```json
// lint
    "python.linting.flake8Args": [ 
        "--max-line-length=200", 
        "--ignore=E501",        // too many line error
        "--ignore=E402",        // module level import not at top of file error
				"..." ],      
    "editor.rulers": [
        200
    ],
```
{% endraw %}




#### Settings


There are several settings you can configure to customize the behavior of this extension.


| **Settings**                  | **Default**                                                                                                                              | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **`flake8.args`**             | []                                                                                                                                       | Arguments passed to Flake8 for linting Python files. Each argument is a separate string in the array.
e.g "flake8.args": ["--config="]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **`flake8.cwd`**              | ${workspaceFolder}                                                                                                                       | Sets the current working directory used to lint. 
By default, it uses the root directory of the workspace `${workspaceFolder}`. 
You can use the parent folder as the working directory by setting it to `${fileDirname}`.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **`flake8.severity`**         | { "convention": "Information", "error": "Error", 
"fatal": "Error", 
"refactor": "Hint", 
"warning": "Warning", 
"info": "Information" } | Mapping message types to diagnostic severity levels. You can also override specific Flake8 error codes.
e.g { "convention": "Information", "error": "Error", "fatal": "Error", "refactor": "Hint", "warning": "Warning", "W0611": "Error", "undefined-variable": "Warning" }                                                                                                                                                                                                                                                                                                                                                                                                         |
| **`flake8.path`**             | []                                                                                                                                       | Path or command to be used by the extension to lint. Single or multiple string arrays. Each argument is a separate string in the array.
If set to ["flake8"], it will use the version of Flake8 available in the PATH environment variable.
**Note**: Using this option may slowdown linting.
e.g. - "flake8.path" : ["~/global_env/flake8"]- "flake8.path" : ["conda", "run", "-n", "lint_env", "python", "-m", "flake8"]- "flake8.path" : ["flake8"]- "flake8.path" : ["${interpreter}", "-m", "flake8"]
This also supports the `${interpreter}` variable as one of the entries of the array. This variable is substituted based on the value of the `flake8.interpreter` setting. |
| **`flake8.interpreter`**      | []                                                                                                                                       | Path to the Python executable or command used to start the Flake8 server and child processes.
Array of single or multiple strings. Each argument is provided as a separate string in the array.
If set to `[]`, the path of the selected Python interpreter is used.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **`flake8.importStrategy`**   | useBundled                                                                                                                               | Define the Flake8 binary to use for linting.
If set to `useBundled`, the included Flake8 binary will be used.
When set to `fromEnvironment`, attempts to use the Flake8 binary and all dependencies available in the currently selected environment.
**Note**: If the extension can't find a valid Flake8 binary in the selected environment, it will fallback to using the Flake8 binary that is shipped with the extension. This setting will be overridden if `flake8.path` is set.                                                                                                                                                                                               |
| **`flake8.showNotification`** | off                                                                                                                                      | Controls when notifications are shown by this extension. Accepted values are onError, onWarning, always and off.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **`flake8.ignorePatterns`**   | []                                                                                                                                       | Configure [glob patterns](https://docs.python.org/3/library/fnmatch.html) as supported by the fnmatch Python library to exclude files or folders from being linted with Flake8.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **`flake8.enabled`**          | true                                                                                                                                     | Specifies whether to enable or disable linting Python files. This setting can be applied globally or at the workspace level.
When disabled, the linting server itself remains active and monitors read and write events, but does not perform linting or expose code operations.                                                                                                                                                                                                                                                                                                                                                                                                     |

undefined
The following variables are supported for substitution in the `flake8.args`, `flake8.cwd`, `flake8.path`, `flake8.interpreter` and `flake8.ignorePatterns` settings:

- `${workspaceFolder}`
- `${workspaceFolder:FolderName}`
- `${userHome}`
- `${env:EnvVarName}`


## Git hook for `flake8`


---


A **Git hook** is a function in Git that executes a specific script at an event. A [**pre-commit**](https://rebedy.github.io/posts/Git-pre-commit-Hook/) is a hook that runs before committing. [Lint](https://rebedy.github.io/posts/Coding-Convention-5-Linter/) can be performed automatically through pre-commit.



### 1. Create configuration file for Git hook


The `.git/hooks/pre-commit` file will be created with the command below. 



{% raw %}
```bash
flake8 --install-hook git
```
{% endraw %}



You can set the strict option or lazy option.



{% raw %}
```bash
git config --bool flake8.strict true
```
{% endraw %}



_* If lint fails using the strict option, the commit will not be made and you can see the lint results instead._



{% raw %}
```bash
git config --bool flake8.lazy true
```
{% endraw %}



_* Only staged files can be inspected using the lazy option. If the lazy option is false, all tracked files are checked._



## References


---

- [https://bitrader.tistory.com/340](https://bitrader.tistory.com/340)
- [https://velog.io/@juheesvt/vscode에서-flake8-사용하기](https://velog.io/@juheesvt/vscode%EC%97%90%EC%84%9C-flake8-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)
