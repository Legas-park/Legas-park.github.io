---
title: If Statements
tags:
- beginner
- learnjava
- HackerRank
categories:
- Javaclass
- SolveTest
- Posting
toc: true
toc_sticky: true
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
if문 만으로는 복잡한 내용을 처리하는데 어느정도 한계가 있습니다.  
if문을 사용할때는 조건이 true가 되었을때만 실행됩니다.
false가 되었을때 실행시키기 위한 if-else문을 다음과 같이 정의하여 사용할 수 있습니다.

```java
if(조건식){// 조건식이 true일때 아래 실행문 동작
실행문; // ex) System.out.println("정답");
}else{
실행문; // ex) System.out.println("오답");
}
```
if 조건식이 true값을 가질때 중괄호 {}안의 실행문을 동작시킨다.
반대로 조건식의 값이 false일때  중괄호 {}안의 실행문을 동작시킨다.

아래 예시
```java
public static void main(String[] args) {
        int N = 3;
        int B = 2;
        if(N+B==5){
            System.out.println("정답");
        }else{
            System.out.println("오답");
        }
        System.out.println("완료");
    }
```
결과는  
정답  
완료  
2가지 출력  
만약 if조건식이 (N+B==7)이라면 결과는  
오답  
완료  
2가지 출력  
이렇게 if-else문은 실행을 ture일때와 false일때 두가지를 선택하여 실행 할 수 있습니다.

### 2-3 else if문
if문은 1개의 조건식을 사용하고 true일때만 실행문을 실행
if-else 문은 1개의 조건식을 사용하고 ture와 false 두가지의 결과에 따라 실행문을 실행합니다.
`else-if문`은 조건식을 2개이상을 두고 흐름을 제어할 때 더 자유롭고 편리하게 사용할 수 있습니다.
else-if문은 다음과같이 정의합니다.

```java
if(조건식1){// 조건식1 이 true일때 아래 실행문 동작
실행문; // ex) System.out.println("정답");
}else if(조건식2){ //조건식2 가 ture일때 아래 실행문 동작
실행문; // ex) System.out.println("홀수");
}else{ // 위의 조건식이 false일때 아래 실행문 동작
실행문; // ex) System.out.println("완료");
```

else-if 문은 여러번 정의할 수 있고 else는 생략할 수 있습니다.  
단, if문이 첫번째, else if가 두번째, 마지막으로는 else가 나와야합니다.
  
아래 예시
```java
public static void main(String[] args) {
        int N = 3;
        int B = 2;
        if(N+B==6){
            System.out.println("정답");
        }else if(N%2==1){
            System.out.println("홀수");
        }else{
            System.out.println("오답");
        }
        System.out.println("완료");
    }
```
결과는  
홀수  
완료  
2가지가 출력되었습니다.   
이렇게 첫번째 조건식이 false일때 else로 넘어가지않고 2번째 조건식으로 실행문을 동작시킵니다.
만약 2번째 조건식 `else if`가 (N%2==0)이라면  
결과는  
오답  
완료  
2가지가 출력됩니다.  
이렇게 else-if문은 조건식을 2가지 이상 추가하여 동작시킬 수 있습니다.

# 2. 문제풀이
이전 포스팅인 Scanner클래스의 문제 사용하여 이번 문제는 if문을 사용하는것입니다.

*Input N의 정수가 주어질때 아래의 조건을 갖추어 실행
1. N이 홀수일때 Weird를 출력  
2. N이 짝수이면서 2~5사이의 숫자일경우 Not Weird를 출력  
3. N이 짝수이면서 6~20사이의 숫자일경우 Weird를 출력  
4. N이 짝수이면서 20보다 큰경우 Not Weird를 출력  

*Input는 양의 정수N이 입력됨
*범위는 1~100사이
*예시 Input이 3일 경우 Output는 Weird
(3은 홀수이므로 1번조건에 따라서 Weird출력)
*예시 Input이 24일 경우 Output 는 Not Weird
(24는 짝수이면서 20보다 크기때문에 4번조건에 따라  Not Weird 출력)

제가 문제를 풀었던 코드는 아래와 같습니다.

```java
public static void main(String[] args) {
        int N = scanner.nextInt();
        if (N%2==0 & 1 < N & N < 6 ) { // 짝수이면서 2~5사이의 숫자
            System.out.println("Not Weird");
        } else if (N%2==0 & N > 5 
				& N < 21) { // 짝수이면서 6~20사이의 숫자
            System.out.println("Weird");
        } else if (N%2==0 & N > 20) { // 짝수이면서 20 이상의 숫자
            System.out.println("Not Weird");
        } else{
            System.out.println("Weird");
        }

        scanner.close();
    }
}
```
Input의 어느숫자를 입력해도 조건 모두 갖춰진상태로 출력됨
위의 풀이시 여러가지 문제가 되었던점을 아래에 예시로 쓰겠씁니다.

조건 1의 홀수이면서 Weird를 출력하라해서
단순히 조건의 순서대로만 생각하여 코드를 작성한게 문제 1
```java
if (N%2==1){ /// N의 정수를 2를 나눈 나머지가 1이되면 홀수이기때문
    System.out.println("Weird");
    }else if (N%2==0){
    System.out.pirntln("Not Weird");
		}else{
		System.out.println("Weird")
		}
```

조건 1~4가 영어로 되어있어 제대로이해하지 못하고  
홀수와 짝수만 구분하면 되는줄알고 한참 해맸습니다 ㅠㅠㅠ...  
문제풀이의 기본은 지문을 잘 읽는것이네요...!  

화이팅! 하며 다음 문제로 포스팅하겠습니다.
