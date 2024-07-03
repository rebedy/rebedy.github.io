---
layout: post
date: 2024-06-14
title: "Guideline [1]: MISRA C "
tags: [guideline, safety-related standards, ICMS, MISRA C, C, C++, ]
categories: [Guideline/Assessment, ]
math: false
---



## [MISRA C Guideline](https://misra.org.uk/)?


---


![0](/assets/img/2024-06-14-Guideline-[1]:-MISRA-C-.md/0.png)



#### [MISRA C:1998 - Reference Guide](https://wwwfiles.iar.com/rl78/EW_MisraC1998Reference.pdf)


Coding rules based on car model.


**MISRA C** and **ISO26262** are safety-related standards for automotive software and system development.


**Motor Industry Software Reliability Association**, 자동차 산업 소프트웨어 신뢰성 협회)가 1998년, 차량 시스템에서 C언어를 사용하기 위한 일련의 가이드라인을 소개함.


**자동차 산업계를 위한 코딩 규칙**을 세운 가이드라인을 출판하면서 자동차 업계에서 사용하는 C언어 프로그래밍 언어의 애매함(ambiguities)를 다루며 생겨났다.


“Development Guidelines for Vechile based Software (차량 기반 소프트웨어에 대한 개발 가이드라인)”이 바로 MISRA C이다. MISRA C는 차량 내 소프트웨어 안전성이 중요해 지면서 소프트웨어의 결함을 줄이기 위해 탄생했다.


가이드라인들은 변수 또는 함수의 선언, 정의, 제어 흐름, 포인터, 배열, 구조체, 공용체, 표준 라이브러리를 포함하는 17개의 섹션으로 분류된다. 이러한 가이드라인들은 준수 필요 정도에 따라 아래와 같이 분류된다.

- Mandatory Rule: MISRA C의 일부 코딩 규칙들은 예외(deviation)없이 직관적이고 명확하다. 이와 같은 규칙들은 어떠한 상황에서도 예외가 허용되지 않는다.
- Required Rule: MISRA C를 준수하도록 요구 받는 코드는 반드시 Required Rule들을 준수해야 한다. 이 규칙들은 정당한 사유 있을 경우에 한해서 예외가 허용된다.
- Advisory Rule: 권장사항. 하지만 이 규칙들이 무시되어도 된다는 뜻은 아니며 합리적으로 준수되어야 함을 의미한다.

이후로도 수시로 **업데이트** 되고 있다.

- **MISRA C 1998 (MC1):** "Guidelines for the use of the C language in vehicle-based software"
	- 127개 규칙 / 93개 필수규칙 / 34개 권고규칙
- **MISRA C 2004 (MC2) :** "Guidelines for the use of C language in critical systems"
	- 141개 규칙 / 121개 필수규칙 / 20개 권고규칙
	- MC1에의 단점을 개선함 (불명확한 규칙, 의미 해석이나 적용이 어려운 규칙 등)
- **MISRA C 2012 (MC3) :** "Guidelines for the use of the C languate in critical systems"
	- 143개 규칙 / 28개 권고사항
	- 전자제어장치 등 소프트웨어에 대한 의존성이 급격함에 증가함에 따라 자동차분야 및 여러 분야에서 C 언어에 대한 코딩 표준으로 <u>MISRA C 2012가 가장 널리 사용되고 있다</u>.

현재에는 자동차 산업 뿐만 아니라 안전이 중요한 다른 다양한 응용 분야(의료 및 항공)에서도 사용되고 있으며 산업 표준으로 널리 채택되고 있다.


MISRA C가 확장된 MISRA C++가 2000년 대에 새롭게 C++에 대한 가이드라인으로서 소개됨.



### Why do we need MISRA C?


임베디드 개발자들은 단점이 없는, 이상적인, 무결점의 프로그래밍 언어는 없다는 사실을 알고 있다. 하여 개발자들은 항상 주어진 요구사항에서 가장 최적화된 해결방법을 고민한다.


임베디드 시스템 개발을 목적으로 생겨난 프로그래밍 언어들 예를 들면, PL/M, Forth, Ada, Rust와 같은 언어들이다. 하지만 이러한 언어들은 모두 널리 사용되긴 했지만 보편화되어 있진 않다. 일반적인 임베디드 시스템에서는 C 언어를 채택하여 사용한다.


C 언어는 가장 널리 사용되는 프로그래밍 언어로써 간결하고 표현력이 풍부하며 강력하다. C 언어는 개발자들이 효율적이며, 읽기 쉽고 유지 관리가 용이한 코드를 쉽게 작성할 수 있도록 한다. 하지만 C 언어로 작성된 프로젝트는 치명적인 버그를 가지고 있을 수 있으며, 이러한 버그들은 개발 프로젝트의 모든 단계와 배포에 있어서 시스템에 심각한 문제를 일으킬 수 있다. 특히, 안전 또는 보안이 최우선인 어플리케이션에서는 이러한 C 언어의 단점을 잘 확인해야 한다.



#### Instability of the C programming language


**1.  프로그래머의 실수**

- 단순 타이핑 에러
- 알고리즘 잘못 이해
- 언어 구성소의 원리를 잘못 이해

**2. 컴파일러가 프로그래머가 예상한 것과 다르게 동작**

- C 언어에 완전하게 정의되지 않은 영역이 있어 컴파일러에 따라 동작이 달라질 수 있다.

**3. 컴파일러 자체 에러**

- 컴파일러 자체에 버그를 포함하고 있거나 언어 표준을 준수하지 않을 수 있다. 
컴파일러도 누군가 개발한 소프트웨어 도구이기 때문이다.

**4. 런타임 에러**

- C 언어는 코드 실행 중 생긴 문제를 발견하고 조치를 취하는 런타임 checking에 취약하다.
- 산술 예외, 오버플로우, 포인터 주소 유효, 어레이 바운드 err 같은 런타임 checking 제공 안함.
undefined

## Why MISRA needed to be updated?


---

- Are the new rules are necessary?
- Is it much better than the previous rule?
- Can the code that complies with the existing MC1/MC2 comply with the new standard?

룰이 업데이트 되기 이전에 **언어의 버전도 계속 업데이트** 되기 때문에 위와 같은 의문이 생긴다.


이전 버전의 룰은 C90을 따랐지만 MISRA C 2012는 C90을 강요하지 않도록 결정했다.


예를 들어 C99기능 중 **inline 함수와 _Bool 타입**과 같은 기능이 가치 있는 내용이 인정했기 때문이다.



### What characteristics exist in coding rules?


**Rule Definition**


**Jargon**


**Mandatory Rules**


**Enforceability**


**Scope and Compliance**


**Decidability**


**Migration**



## What’s in the updated MISRA C


---



#### **규칙의 정의 (Rule Definition)**


MISRA C 2012에는 기존에 존재하던 룰들이 서로 다른 해석으로 이해되지 않도록 내용이 추가되었다.

- Amplification - 코딩 규칙 요구 사항의 상세한 설명
- Rationale - 규칙이 필요한 이유에 대한 설명
- Exceptions - 규칙의 요구 사항이 적용되지 않는 특정 상황
- Examples - 준수 및 위반에 대한 코드 예제


#### 특수 용어(**Jargon)**


코딩 규칙을 정의하는데 추가적인 용어 도입이 필요할 수 있다.


**(1) MC2**

- underlying type: C++에서 다른 의미로 사용됨
- complex expression: 일반적으로 C99에서 지원되는 대수를 의미하는데 사용됨

**(2) MC3**

- essential type: 산술 표현의 타입을 설명할 때 더 직관적이다.
- composite expression: 모호한 표현을 벗어남


#### **필수규칙 (Mandatory Rules)**


이전 버전은 두 카테고리로 룰을 분류했다. (**Required Rules**, _**Advisory Rules**_)


또한 정식 예외 사항이 아닌 이상 모든 **Required Rules**을 준수해야만 한다.


_**Advisory Rules**_는 완화된 항목이며, **정식 예외**는 선택 적용되었다.


이는 주관적인 판단이 반영되는데 아래와 같은 요소들을 고려해야 한다.

- 코딩 규칙의 위반이 소프트웨어 결함을 얼마나 발생 시키는가?
- 코딩 규칙의 위반이 얼마나 자주 발생하는가?
- 코딩 규칙이 안전한 코드에 대해 irksome(귀찮은) 제약 사항을 요구하는가?

하지만 일부 규칙들은 예외 없이 명확하다. 
**`MC3`**는 이들을 _**Mandatory Rules**_로 분류하며 예외가 허용되지 않는다.



#### **시행 가능성 (Enforceability)**


코딩 규칙은 잠재 결함을 줄일 수 있는 안전한 언어 subset을 정의하는 것이다.


정적 분석 도구는 코딩 규칙 적용 뿐 아닌 해결되지 않는 에러의 검출을 돕는다.


_정적 분석 도구 필요 :_

1. _불확실성의 제거_
2. _시간 절약_
3. _코드 개발시 빠르게 피드백 제공_
4. _매뉴얼 코드 리뷰와 관련된 문제점 완화_

다만 코딩 표준에서 정적으로 실행이 불가능한 규칙이 있다. 문서, 프로세스, 주관적 해석 등이다.


코딩 표준이지만 자동 분석에 의존할 수 없는 부분들 이다.


따라서 **`MC3`** 에서는 **규칙(rules)**와 **지침(directives)**으로 용어를 구분했다.


**규칙**은 요구 사항에 대한 자세한 설명이 동반되며 정적 분석 도구 규칙의 준수를 검사할 수 있어야 한다.



#### **범위와 준수 (Scope and Compliance)**


간단한 규칙들은 한 문장의 문법을 검사하는 것으로 쉽게 수행될 수 있지만 복잡한 규칙들은 제어 구문, 함수 전체, 프로젝트 단위의 분석이 요구된다.


분석의 범위를 설정하기 위해 **`MC3`**의 규칙들은 **System Rule**, **Single Translation Unit Rule**로 분류된다.



#### **결정 가능성 (Decidability)**


일부 코딩 규칙은 본질적으로 결정이 불가능(**undecidable**)하다.


결정이 가능한 규칙(**decidable**)이란 어떠한 상황에서도 도구를 통해 규칙 위반 규명이 가능한 것을 말한다.


아래 두 가지 대답 중 하나가 가능한 것이다.

1. Yes - 규칙 위반은 분명히 이 시점에서 발생한다.
2. No - 규칙 위반은 분명히 이 시점에서 발생하지 않는다.

**`MC3`**에 있는 모든 규칙들은 명확하게 **decidable**과 **undecidable**로 분류된다.


143개 Rule 중 28개가 **undecidable**로 분류되며 **undecidable** 일 때 절대로 준수를 보장할 수 없다.



#### **마이그레이션 (Migration)**


`MC2`를 준수해서 개발한 코드에서 **`MC3`**가 영향을 끼치는 경우는 없을까?


영향이 없어야 될 것이다.


아래의 제약 사항의 경우 코딩 규칙의 신뢰성은 훼손될 수 있다.

- 알려진 소프트웨어 결함을 바로 지적하지 않은 경우
- 규칙을 회피하는 것이 더 큰 문제를 야기 시키는 경우
- 완벽하게 안전한 코드를 위해 너무 많은 제약을 가하는 경우

**`MC3`**에서는 일부 코딩 제약 사항을 수정/제거함으로써 완화 시켰다.



## Software for coding rules


---



#### Perforce(구 PRQA) 사의 [Helix QAC](https://www.perforce.com/products/helix-qac)


MISRA C/C++ 뿐 아닌 AUTOSAR C++ 14, JSF AV C++ 도 검증할 수 있다.


이는 매우 정확한 언어 분석 및 이해력을 가졌으며, Data Flow 기능과 결합되어있다.


이를 통해 언어 사용해 의해 발생되는 여러 문제들을 식별하며 코딩 룰 준수를 위한 수행 방안을 제공한다.



### 정적 분석 자동화 도구


일반적으로 MISRA C 코딩 가이드라인 준수 여부는 정적 분석 자동화 도구를 통한 정적 검증을 통해 확인 할 수 있다.



#### 대표적인 정적 분석 소프트웨어 툴.

- **MathWorks 사의 “Polyspace”**
- **Simulink 사의 “Code Inspector”**

임배디드 개발자들은 정적 검증의 결과로서 MISRA C를 위배하는 코드가 발견되면 위배된 가이드 라인과 그에 따른 적절한 코드 수정을 확인 할 수 있다.

