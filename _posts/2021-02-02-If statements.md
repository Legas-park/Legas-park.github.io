---
title: If Statements
---

안녕하세요 레가스입니다. :)

두번째 해커랭크에서 문제를 풀면서 풀이중 몰랐던 내용과 문제를 풀었던 내용을 포스팅하겠습니다.

# 1. If Statements
조건문은 작성한 코드를 조건에 따라서 코드의 실행 흐름을 다르게 동작하도록 제어하는 것 입니다.  
예를들어서 1번 조건의 실행과 2번조건의 실행을 서로 다르게 동작시킬 수 있는 것입니다.

조건문에는 크게 두가지고 나누어지는데 If와 Switch 입니다.
저는 If 문제를 풀었기 때문에 If에 대한 내용을 포스팅하도록 하겠습니다.

## 1-1 If문의 종류
If Statements는 총 3가지로 다시 구분할 수 있습니다.
1. If
2. if - else
3. else if

### 2-1 If Statements
if문은 다음과 같이 정의하여 사용합니다.
```java
if(조건식){// 조건식이 true일때 아래 실행문 동작, false면 미실행
조건식; // ex) System.out.println("정답");
}
```
조건식이 true값을 가질때 중괄호 {}안의 실행문을 동작시킨다.
반대로 조건식의 값이 false일때 if문을 실행시키지 않고 패스함.

아래 예시
```java
public class Main {

    public static void main(String[] args) {
        int N = 3;
				int B = 2;
				if(N+B==5){
				    System.out.println("정답");
				}
       System.out.println("완료");

    }
}
```
결과는
정답
완료
2가지 모두 출력되었습니다.
만약 if문의 값이 false일 경우 결과는
완료만 출력됩니다.

  
조건문안에는 또다른 조건문이 들어갈 수 있습니다.
아래 예시
```java
public class Main {

    public static void main(String[] args) {
        int N = 3;
        int B = 2;
        if(N+B==5){
            System.out.println("정답");
            if(N+3==6){
                System.out.println("2번째 정답");
            }
        }
        System.out.println("완료");
    }
}
```
결과는
정답
2번째정답
완료
3가지 모두 출력되었습니다.
만약 if문 안의 if문의 값이 false일 경우 if안의 if는 패스하게 됩니다.
결과는
정답
완료

재밌네요!

### 2-2 if - else문
