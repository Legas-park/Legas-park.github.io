---
title: Variables(변수)
categories:
- Javaclass
tags:
- beginner
- learnjava
toc: true
toc_sticky: true
---

안녕하세요 Legas입니다. :)

이제 코딩에 대한 부분을 시작했으니 다음단계로 넘어가서 Java언어에 대한 공부를 쭉 이어나가겠습니다.

# 1. Variables
변수란 
`계속 변하는 값이면서, 그 값을 저장하는 공간.`
------
변수가 가지는 type는 아래와 같습니다.
Primitive Type: 아래 표에 정의된 값을 저장
Reference Type: 복잡합 개체(날짜, 문자열 등)를 저장 할 수 있음

|**Primitive Type**|**Data**    |**Memory Size**|**Description**|
|:---|:---|:---:|:---|
|byte|정수|1 byte|-128 ~ 127 값을 저장|
|short|정수|2 byte|-32,768 ~ 32,767 값을 저장|
|int|정수|4 byte|	-2,147,483,648~2,147,483,647 값을 저장|
|long|정수|8 byte|-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 값을 저장|
|float|실수|4 byte|	±(1.40129846432481707e-45 ~ 3.40282346638528860e+38)값을 저장|
|double|정수|8 byte|±(4.94065645841246544e-324d ~ 1.79769313486231570e+308d)값을저장|
|char|문자|2 byte|모든 유니코드 문자 표현 가능|
|boolean|참과 거짓|1 byte|참과 거짓표현 가능|

# 2. 실습
```java
package com.pakage;

public class Main {

    public static void main(String[] args) {
        int age = 31;
        // int형 타입의 변수를 사용하여 aeg = 31이라는 정수를 사용하여 선언합니다.
        // 선언은 age 를 =연산자를 사용하여 정수인 31로 데이터를 저장해주는것입니다.
        System.out.println(age);
        // age = 31로 변수를 선언했으니 출력은 31이 나올것입니다.
    }
}
```
![]({{ 'assets/images/Post2/img12.JPG' | relative_url }})
완벽하네요!
두번째 코딩에 성공하였습니다. :)

이제 선언한 변수의 age값을 변경해보겠습니다
```java
public class Main {

    public static void main(String[] args) {
        int age = 31;
        age = 34;
        System.out.println(age);

    }
}
```
출력은 변경된 34와 동일한 값이 나옵니다.

## 2-1 변수에 변수 추가
```java
    public static void main(String[] args) {
        int age = 31; // age 변수를 31로 선언
        System.out.println(age); // age 출력 값은 31
        int myAge = age; // myAge 변수를 age변수로 선언
        System.out.println(myAge); // myAge변수에 저장된 출력 값은 31
        age = 34; age // 변수 값 변경 34
        System.out.println(age); // age 변수에 저장된 출력 값은 34
        System.out.println(myAge); // myAge 변수에 저장된 출력 값은 31

    }
}
```
위의 실습에서 변수`age`의 값을 변경했을때 변경된 변수값으로 출력을했는데
변수`age`를 선언하고 새로운 변수`myAge`에 저장된 변수`age`로 선언을 했더니 그 값을 그대로 복사함
이후 처음 선언된 변수 `age`를 변경한 후 출력했더니 처음 선언된 값인 31로 출력됨

이처럼 *Primitive type*은 저장된 값을 공유하지 않고 복사하여 사용됩니다.

## 2-2. 참조형 타입
참조형 타입은 *Primitive type*과 다르게 저장된 값을 공유하여 사용됩니다.
```java
public static void main(String[] args) {
        Point point1 = new Point(1,1);
        Point point2 = point1;
        point1.x = 2;
        System.out.println(point2);

        int a = 1;
        int b = a; // 변수 선언
        a = 3; // 기존변수 값을 변경
        System.out.println(b); // 결과는 변경된 값 3이 출력되지않고 기존변수 1이 출력됨

      }
```
위처럼 `Point`클래스를 사용한 변수 `point1.x`값을 변경해도 참조타입의 경우
변경된 값을 참조에 의해 복사되는 반면에 기본유형은 처음 선언한 값을 계속 가지고있습니다.
