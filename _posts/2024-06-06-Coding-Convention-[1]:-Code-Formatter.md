---
layout: post
date: 2024-06-06
title: "Coding Convention [1]: Code Formatter"
tags: [coding-convention, code-formatter, black, prettier, autopep8, ]
categories: [Coding Convention, ]
math: false
---



## Coding Convention


---


![0](/assets/img/2024-06-06-Coding-Convention-[1]:-Code-Formatter.md/0.png)_https://overcome-the-limits.tistory.com/5_


**코딩 컨벤션(코드 작성 스타일 규칙)?**


코딩 컨벤션은 프로그래밍을 할 때 제시되는 가이드라인이다. 코딩 컨벤션에는 여러가지가 있는데, 어떤 것을 따르던지 한 프로젝트에서는 통일된 컨벤션을 준수해야 한다. 코딩 컨벤션은 indentation, 주석 처리, 선언문, 공백 문자, naming convention, 프로그래밍 원칙 등등 여러가지 가이드라인을 제시한다.


**Coding conventions?**


Coding conventions are guidelines presented for programming. There are many different coding conventions, but no matter which one you use, a unified convention must be observed in a project. Coding conventions include various guidelines such as indentation, comment processing, declarations, whitespace characters, naming conventions, programming principles, etc.



## What is Code Formatter?


---


![1](/assets/img/2024-06-06-Coding-Convention-[1]:-Code-Formatter.md/1.png)_https://nx006.tistory.com/62_


**개발자가 작성한 코드를 정해진 코딩 컨벤션(코드 작성 스타일 규칙)을 따르도록 변환 해주는 도구.**


코드 포멧터를 통해 일관된 코드 스타일을 유지함으로써 코드 가독성을 높이고 개발자들 간의 원활한 커뮤니케이션을 유도한다. 코드를 저장 시 정해놓은 규칙에 맞게 자동으로 정렬해서 코드 스타일을 통일한다.


**A tool that converts code to follow established coding conventions(code writing style rules).**


By maintaining a consistent code style through the code formatter, you can improve code readability and encourages smooth communication between developers. It unifies and arranges the code style when saving the code according to the rules set.



### Purpose of Code Formatter



#### (1) Promise for collaboration



#### (2) Readable code is a good code



#### (3) Reduce concerns about style standards



## How to use formatter


---

- Find problems in command-line and let the code formatter to modify.
- Let the code formatter to modify everytime the file is saved on IDE.


### **Pre-requisites**


![2](/assets/img/2024-06-06-Coding-Convention-[1]:-Code-Formatter.md/2.png)

1. `C/C++`
	1. Microsoft. C/C++ IntelliSense. Debugging, and code browsing.
2. `Clang-Format`
	1. Xaver Hellauer. Clang-Format in Visual Studio Code.


### How to use?

- Just install two extensions on your IDE!
- If you were using clang extension, it will collide with C/C++ extension so we need to deactivate or erase ‘clanged’.


## Code Formatters


---



### [C++]



#### Settings

1. Command palette (macOS: `⇧⌘P`, Linux: `Ctrl+Shift+P`)
2. **`Preferences: Open User Settings (JSON)`**
3. Open `settings.json` file.
4. Add. (example of Google formatter)


{% raw %}
```json
// Define basic formatter.
"editor.defaultFormatter": "ms-vscode.cpptools",

// Format the code when the file is saved.
"editor.formatOnSave": true,

// Define the code formatting style.
"C_Cpp.clang_format_fallbackStyle": "Google",
```
{% endraw %}




#### **C++ Coding Conventions**


C++ 프로젝트를 진행한다면, 이러한 코딩 컨벤션 중 하나를 택하거나 아니면 프로젝트를 진행하는 사람들과 컨벤션에 합의를 보고 통일된 컨벤션으로 코딩을 해야 한다.


If you are working on a C++ project, you must either choose one of these coding conventions or agree on a convention with the people working on the project together.


**(1) LLVM:** [LLVM coding standards](https://llvm.org/docs/CodingStandards.html)

- **clang-format:** [**ClangFormat**](https://clang.llvm.org/docs/ClangFormat.html)
	- Code formatter provided as part of the LLVM project
	- [Untitled](https://www.notion.so/b407e4f7e92c451d9536357baf95b884)

**(2) Linux kernel:** [Linux kernel](https://www.kernel.org/doc/html/v4.10/process/coding-style.html)


**(3) GCC:** [GCC C++ Coding Conventions](https://gcc.gnu.org/wiki/CppConventions)


**(4) GNU:** [GNU coding standards](https://www.gnu.org/prep/standards/standards.html)


**(5) Microsoft:** [Microsoft's style guide](https://docs.microsoft.com/en-us/visualstudio/ide/editorconfig-code-style-settings-reference)


**(6) Google:** [Google's C++ style guide](https://google.github.io/styleguide/cppguide.html)


**(7) Chromium:** [Chromium's style guide](https://chromium.googlesource.com/chromium/src/+/refs/heads/main/styleguide/styleguide.md)


**(8) Mozilla:** [Mozilla's style guide](https://firefox-source-docs.mozilla.org/code-quality/coding-style/index.html)


**(9) WebKit:** [WebKit's style guide](https://www.webkit.org/coding/coding-style.html)


**(10) QT:** [Qt Coding Style](https://wiki.qt.io/Qt_Coding_Style)


**(11) Unreal Engine:** [Unreal Engine Coding Standard](https://docs.unrealengine.com/latest/INT/Programming/Development/CodingStandard/)


**(12) Blender:** Blender Coding Style(http://wiki.blender.org/index.php/Dev:Doc/Code_Style)


**(13) Blink:** [Blink Coding Style Guidelines](https://www.chromium.org/blink/coding-style)


**(14) Inkscape:** [Inkscape Coding Style](https://inkscape.org/en/develop/coding-style/)


**(15) CppCoreGuidelines:** [CppCoreGuidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)

- CppCoreGuidelines is the most representative C++ coding convention[[1](https://ccss17.netlify.app/programmerbase/codingconvention/#cc-indentation-style)]


### [Python]


**(1)** [Coding Convention [5]: Linter](https://www.notion.so/111a6cdb56864b7e858c2199d412a84a) : A small program that checks coding conventions and code errors


**(2)** [**PEP8**](https://rebedy.github.io/posts/Coding-Convention-4-autopep8/#pep8) : coding convention: [Style Guide for Python Code](https://peps.python.org/pep-0008/) / [PEP8 한국어 번역](https://zerosheepmoo.github.io/pep8-in-korean/doc/introduction.html) 


**(3)** [**autopep8**](https://rebedy.github.io/posts/Coding-Convention-4-autopep8/#autopep8) : A module that automatically corrects Python code to PEP8 conventions.


**(4)** [**Black**](https://rebedy.github.io/posts/Coding-Convention-2-Black/) : the uncompromising Python code formatter


**(5) Google** :  [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html). Quite commonly used!



### [JAVA]


**(1)** [**Prettier**](https://rebedy.github.io/posts/Coding-Convention-3-Prettier/)



## Safety-related standards and Code Formatter


---


**ISO26262**와 **MISRA C**는 자동차 소프트웨어 및 시스템 개발에 있어 안전성 관련 표준으로 두 표준 모두 코드의 안전성, 유지 보수성, 가독성에 중점을 둔다.


**Code formatter** 자체는 코드의 스타일을 통일하여 가독성을 높이는 도구로, **MISRA C** 또는 **ISO26262**를 직접 준수하도록 설계되지는 않았다. 그러나 일부 <u>정적 코드 분석 도구</u>는 **MISRA C** 규칙을 준수하는지 검사하는 기능을 제공한다.


**MISRA C**나 **ISO26262**와 같은 표준을 준수하려면 단순한 코드 포맷터만으로는 충분하지 않다. <u>코드 검사 및 정적 분석 도구를 함께 사용</u>하여 규칙 위반을 발견하고 수정하는 것이 필요하다.


개별 프로젝트나 조직의 요구 사항에 따라 적절한 도구를 선택하는 것이 중요하다. 따라서 도구를 선택하기 전에 해당 도구가 자신의 프로젝트나 <u>조직의 특정 요구 사항을 충족하는지 확인</u>하는 것이 좋다.


**ISO26262** and **MISRA C** are safety-related standards for automotive software and system development and both standards are focused on safety, maintainability, and readability of code.


The **code formatter** itself is a tool that improves readability by unifying the style of the code, and is not designed to directly comply with **MISRA C** or **ISO26262**. However, some <u>static code analysis</u> tools provide the ability to check for compliance with MISRA C rules.


To comply with standards, a simple code formatter is not enough. <u>It is necessary to use a combination of code inspection and static analysis tools</u> to discover and fix rule violations.


It is important to choose the appropriate tool based on <u>the needs of the individual project or organization</u>. So we need to make sure it meets the specific needs of the project or organization.

1. [**Clang-Format**](https://clang.llvm.org/docs/ClangFormat.html)
	1. A part of the LLVM project, the C, C++, and Objective-C code formatter.
	2. 이 도구는 확장성이 뛰어나고 많은 설정 옵션을 제공하므로, 다양한 코딩 가이드라인에 맞게 조정할 수 있다. 또한 MISRA C나 ISO26262와 같은 표준의 모든 요구 사항을 충족시키기 위해 설정을 조정할 수 있다.
	This is highly extensible and offers many configuration options, so it can be adapted to different coding guidelines. And you can adjust the settings to meet all requirements of standards such as MISRA C or ISO26262.
2. [**Astyle**](https://astyle.sourceforge.net/astyle.html) **(Artistic Style)**
	1. A Free, Fast, and Small Automatic Code Formatter for C, C++, C#, and Java Source Code
	2. Astyle can also be adjusted to suit various coding styles through settings.
3. [**Uncrustify**](https://github.com/uncrustify/uncrustify)
	1. A source code beautifier for C, C++, C#, Objective-C, D, Java, Pawn and Vala.
	2. This tool offers a wide variety of configuration options, allowing you to <u>precisely</u> control your code style.


#### The static code analysis tools that support MISRA C

1. **PC-lint/FlexeLint**
	1. Provides a function to check compliance with MISRA C and MISRA C++ rules.
2. **LDRA**
	1. Provides the ability to check MISRA C and ISO26262 rules.
3. **Coverity**
	1. Synopsys’ Coverity also supports MISRA C and ISO26262.
4. **SonarQube**
	1. Provides a plug-in to check compliance with MISRA C and ISO26262.
5. **PRQA (now part of Perforce)**
	1. Provides the ability to check compliance with MISRA C and several other coding standards.


## References


---

- [https://ccss17.netlify.app/programmerbase/codingconvention/#cc-indentation-style](https://ccss17.netlify.app/programmerbase/codingconvention/#cc-indentation-style)
- [https://nx006.tistory.com/62](https://nx006.tistory.com/62)
