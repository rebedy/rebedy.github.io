---
layout: post
date: 2024-06-07
title: "Coding Convention [2]"
tags: [coding-convention, code-formatter, black, ]
categories: [Coding Convention, ]
---



## [Black](https://black.readthedocs.io/en/stable/)


---


코드 스타일을 통일 시켜 주는 code formatting tool


[https://github.com/psf/black](https://github.com/psf/black)


![0](/assets/img/2024-06-07-Coding-Convention-[2].md/0.png)



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

- Black을 기본 포맷터로 실행하도록 VSCode 기본 설정에 추가
	- Go to `.vscode/setting.json` in the command palette(`ctrl+shift+P`).
	- Add commands below.


{% raw %}
```bash
"python.formatting.provider": "black“, # VSCode의 기본 포맷터 대신 Black을 사용하게 해주는 설정
"editor.formatOnSave": true, # 코드를 저장할 때 마다 자동으로 포맷팅 해주는 설정
```
{% endraw %}




## Options


---

- `l` : 한 라인에 최대 글자 수 (초기값 88)
- `—diff` : 파일을 변경하지 않고 변경되는 부분을 콘솔로 보여 준다.
- `—color` : `—diff`를 사용했을 때 변경점에 색을 입힌다.
- `black {파일명 또는 폴더명} -l 80 --diff --color` 과 같이 사용하면 변경 사항을 preview 할 수 있다.


## **Git hook Setting**


---

- 코드 편집기 설정은 어디까지나 개인의 선택 사항이기 때문에 프로젝트 차원에서 포맷팅이 되지 않은 코드를 커밋하려고 하는 것을 방지하는 것이 바람직하다.


#### 1. Install `pre-commit` package 



{% raw %}
```bash
pip install pre-commit
```
{% endraw %}




#### 2. Generate `.pre-commit-config.yaml` file



#### 3. Add



{% raw %}
```bash
repos:
  - repo: https://github.com/psf/black
    rev: stable
    hooks:
      - id: black
```
{% endraw %}




#### 4. `pre-commit` 

- 방금 작성한 Git hook 스크립트를 설치


{% raw %}
```bash
$ pre-commit install
pre-commit installed at .git/hooks/pre-commit
```
{% endraw %}




#### 5. 코드 에디터의 자동 포맷팅을 해제 후 커밋을 시도



#### 6. Git hook 스크립트가 실행되어 커밋이 실패하고 Black이 포맷팅을 해줌



## How to avoid formatting


---


 **# fmt : off / on / skip**


Code Formatter는 보통 '파일을 저장할 때'나 혹은 '커밋을 생성할 때' 등에 자동 실행되도록 지정한다. 그런데 가끔은 Code Formatter 가 실행되지 않았으면 하는 때가 있다.



{% raw %}
```bash
# fmt: off
--- codes excluded from formatting ---
# fmt: on
```
{% endraw %}



만약 해당 코드 안에서도 특정한 라인만 포멧팅을 회피하고 싶다면 그 라인 끝에 `# fmt: ski`p을 사용할 수도 있다.



## References


---

- [https://www.daleseo.com/python-black/](https://www.daleseo.com/python-black/)
- [https://www.daleseo.com/pre-commit/](https://www.daleseo.com/pre-commit/)
