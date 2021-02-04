---
title: Scanner Stdin and Stdout II
tags:
- beginner
- learnjava
- HackerRank
categories:
- Javaclass
- SolveTest
- Posting
toc: ture
toc_sticky: ture
---

안녕하세요 Legas 입니다. :)

이번 포스팅은 첫번째 문제풀이인 Scanner Class의 응용버전을 포스팅하겠습니다.
이전시간에 이미 문제풀이 전에 정의를 하고왔으니 이번엔 간단하게 설명하고 문제풀이로 넘어가겠습니다.

# 1. Stdin and Stdout
Stdin은 Standard input이라는 뜻이고
Stdout은 Standard output라는 뜻입니다.

지난번 풀이에는 무작위 정수형 int형 타입의 숫자를 입력시  
출력된 실행문에 그대로 나오게 했었습니다.

이번 문제에는 int뿐 아니라 double, String 타입의 코드를 만들어서 출력할 예정입니다.

```java
public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int i = scan.nextInt();
        double d = scan.nextDouble();
        String s = scan.nextLine();



        System.out.println("String: " + s);
        System.out.println("Double: " + d);
        System.out.println("Int: " + i);
    }
}
```

Scanner 클래스를 사용하여 입력값을 int, double, String 타입으로 입력
출력도 입력값과 같이 세가지가 동일하게 나오도록 코드를 만들었습니다.

input 31, 31.2, Name is Legas  
결과는  
String :
Double : 31 .2 
Int: 31
input의 순서대로 입력했지만 31.2를 입력하고 Enter를 누르는순간 실행은 종료됩니다.  

nextInt() 메소드 다음에 nextLine() 메소드를 실행하려고 할때 nextLine() 메소드를 입력받지않고 그냥 넘어가버리는 오류가 발생합니다.  
이유는 `nextInt or double()`메소드를 실행할때 31을 입력했지만 Enter값은 그대로 남아있게됩니다.  
`nextLine()`메소드는 Enter값을 기준으로 메소드를 종료시키기 때문입니다.  
그렇다면 이러한 문제를 해결하기 위해서는 nextint or double()메소드 다음에 nextLine()메소드를 한번 더 써줘서 Enter값을 없애주면 됩니다.

# 2. 문제풀이

* 3개의 input이 있을때 실행값을 출력시켜라

Sample Input
1. 42
2. 3.1415
3. Welcome to HackerRank's Java tutorials!

Sample output
1. String : Welcome to HackerRank's Java tutorials!
2. Double : 3.1415
3. Int : 42

아래 문제를 풀었던 코드
```java
public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int i = scan.nextInt();
        scan.nextLine();
        double d = scan.nextDouble();
        scan.nextLine();
        String s = scan.nextLine();



        System.out.println("String: " + s);
        System.out.println("Double: " + d);
        System.out.println("Int: " + i);
    }
}
```
결과는  
어떠한 정수, 실수, 문자열을 입력해도 샘플 output순서대로 출력이 되었습니다.
![]({{ 'assets/images/img2.JPG' | relative_url }})

이 문제를 풀면서 실수했던 내용을 정리하여 포스팅 시작에 문제점을 미리 썻습니다.
다음 문제풀이에 포스팅을 이어가도록 하겠습니다.
화이팅!
![]({{ 'assets/images/Post Stdin and Stdout/img1.JPG' | relative_url }})
