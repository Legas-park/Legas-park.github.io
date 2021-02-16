---
title: Java Loops I
tags:
- beginner
- learnjava
- HackerRank
categories:
- Javaclass
- SolveTest
toc: true
toc_sticky: true
---

안녕하세요 Legas입니다. :)

오늘도 문제풀이와 풀면서 배운것을 포스팅하겠습니다.

# 1. Loops(반복문)

자바에는 반복문의 사용방법이 몇가지가 있습니다.  
그중 while문 & for문 2가지로 크게 나뉘는데 이번문제 풀이시 사용된것은 for문을 사용했기 때문에 for문에 대해서 내용을 정의하고 문제풀이로 넘어가겠습니다.

# 1-1. for문
같은 내용을 여러번 반복하여 입력할때  특정한 횟수만큼 반복 실행을 하는 경우에 사용된다.
  
for문 정의  
```java
for([1]초기화; [2]종료조건; [3]반복실행){
    [4]반복적으로 실행될 구문
}
```
for문의 동장 순서는 [1] -> [2] -> [4] -> [3] -> [1]...종료조건이 true이면 반복되는 동작이 끝납니다.  

이제 사용법은 아래와 같습니다.  

```java
for(int i = 0; i < 10; i++){
    System.out.print("코딩연습 횟수" + i);
}
```
결과는 
![]({{ 'assets/images/loops/img1.JPG' | relative_url }})

위처럼 반복되는 작업을 수행할때 사용되는 반복문중 하나인 for문입니다.  

# 2. 문제풀이
* Input N의 정수가 주어질때 아래의 조건을 갖추어 실행  
1. 10개의 결과를 출력.
2. 1개의 결과마다 출력은 N x i(i는 1~10까지의 숫자)가 되어야함.
3. 각 결과의 출력 방식은 N x i = result.

Sample Input  
2  

Sample Output  
2 x 1 = 2  
2 x 2 = 4  
2 x 3 = 6  
2 x 4 = 8  
2 x 5 = 10  
2 x 6 = 12  
2 x 7 = 14  
2 x 8 = 16  
2 x 9 = 18  
2 x 10 = 20  

아래 문제를 풀었던 코드

```java
public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
      int a; //인트형 a 선언
      String b; // 문자열 b 선언
      int N = scanner.nextInt(); // input의 정수 N을 입력
          scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");
                  for(int i = 1; i < 11; i++){ //곱하기 10을 하기위해 반복문 사용
          a = N*i;
          b = "x";
          System.out.println(N+" "+b+" "+i+ " "+"="+" "+a);
// Output을 맞추기위해 ""사용하여 중간의 공백을 만듬
       }

        scanner.close();

    }
}
```
위의 문제를 봤을때 for문을 사용해야겠다는 생각이 바로 들었고, 이후 for문 사용까지는 했는데
출력에서 막혔었습니다.  

처음에는 `System.out.println(N x i = a);`했다가 실패..  
두번째는 x(곱하기)부분을 문자열로 해봐야지 `System.out.println(N+b+i=a);` 실패..
세번째는 공백을 추가해야겠다 해서 쓴게 위의 코드입니다.  

하지만 뭔가 많이 부족해보이고 복잡한 내용으로 코드를 완성했지만 좀더 간결하게 사용되는 방법을 알게되어 포스팅에 내용을 적겠습니다.  
`println();` 괄호()안에 들어가는것은 java에서 자동적으로 타입이 다르더라도 문자열로 변환을해서 들어간다는것.  
그렇게되면 다음과 같은 실행문을 사용가능  
```java
System.out.println(N+" x "+i+" = "+N*i)
```
위 코드처럼 사용했다면 `int a;`선언을 안했어도 되고, `String b;` 문자열 선언을 안했어도 되어서 a,b를 초기화하여 실행문을 어렵게 사용할 필요가 없다고 생각이 들었습니다.  

물론 제가 처음에 풀었던 코드가 틀린것은 아니지만 조금더 java의 문법에 많은 공부가 필요하다는것을 배웠습니다.
그외에도 다른방법으로도 풀수 있는 방법이 있지만 일단 공부를 조금 더 하고 나중에 다른포스팅에서 배웠던 부분을 쓰기로 하겠습니다.
.
