---
title: First Java Program<초보>(개발 시작하기)
categories:
- Javaclass
tags:
- beginner
- learnjava
toc: true
toc_sticky: true
---

안녕하세요 Legas입니다. :)

이제 개발프로그램을 통해서 코드를 작성해보고 배우기위해서 공부에 필요한 프로그램을 다운받아야 합니다.

# 1. Installing Java
구글검색에 JDK 다운로드를 검색하여 소프트웨어를 다운받습니다.
<https://www.oracle.com/kr/java/technologies/javase-downloads.html>
포스팅 시점 기준에서는 버전이 Java SE Development Kit 15.0.1 이네요.
사용하는 환경에 따라서 Window & Mac로 받아서 설치하시면 됩니다.

## 1-1. 코드 편집프로그램
코드를 편집하기위해서 여러가시 사용하는 소프트웨어가 있습니다.
Eclipse, VS code, IntelliJ 등등 여러가지 프로그램중에 저는 IntelliJ로 시작했습니다.
(혹시 강의듣는내용이 있다면 강의에 사용하는 소프트웨어를 사용해도 무관합니다.)

## 1-2. IntelliJ 실행
IntelliJ(또는 다른 소프트웨어)를 설치했다면 실행을 합니다.

순서는 꼭 사진의 빨간색 체크표시를 따라서 진행하면 됩니다.
첫번째
![]({{ 'assets/images/Post2/img7.JPG' | relative_url }})

두번째
![]({{ 'assets/images/Post2/img8.JPG' | relative_url }})

세번째
![]({{ 'assets/images/Post2/img9.JPG' | relative_url }})

마지막
![]({{ 'assets/images/Post2/img10.JPG' | relative_url }})

# 2. Coding IntelliJ
개발이 처음이기 때문에 강의나 스터디를 통해서 배우고 강의안에 궁금한것과 기본적인것을 알기위해
왜 코드를 그렇게 사용하고 어떠한 방법으로 진행이 되는지 알기 위해서 기록하여 작성하겠습니다.
![]({{ 'assets/images/Post2/img11.JPG' | relative_url }})

위의 내용을 보면 class의 이름인 Main은 첫글자가 대문자이고 Method의 이름인 main은 첫글자가 소문자입니다.
이것은 개발언어의 규칙대로
class의 이름의 첫 단어는 대문자로 시작되는 파스칼(pascal) 표기법으로 규칙이 정해져있습니다.
Method의 이름의 첫 단어는 소문자로 시작되는 카멜(Camel) 표기법으로 규칙이 정해져있습니다.

지금은 한 단어만 되어있지만 길게 이름을 쓰려면 아래와 같습니다.
```java
public class StudyJavaClass
```
여기서 Study와 Java와 Class의 여러단어가 붙어 사용될때 class의 이름은 첫 글자를 대문자로 표기합니다.

```java
public static void javaClassMain
```
Method의 이름은 java와 Class와 Main의 여러단어가 붙어 사용될때 java의 첫 글자를 소문자로 표기합니다.

이렇게 처음 개발도구로 처음 코딩을 했습니다.
앞으로도 배운것에 대한 내용을 포스팅하고 문제점을 서로 공유하면 좋을것같아요~
