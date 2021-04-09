---
title: EOF and indexOf()
tags:
- HackerRank
- beginner
- learnjava
categories:
- SolveTest
- Javaclass
toc: true
toc_sticky: true
---

안녕하세요 Legas 입니다. :)

이번 포스팅은 EOF와 indexOf()에 대한 포스팅을 하도록 하겠습니다.

EOF는 해커랭크에서 문제를 풀면서 접근하게된 문제이고 indexOf()는 문제를 풀고나서 추가로 공부하면서 알게된 내용을 포스팅하려고 합니다.  

# 1. EOF와 hasNextLine 메소드
EOF란
End Of File 은 더 이상 읽을 데이터가 없어서 여기가 파일의 끝이라는 뜻 입니다.  
EOF의 정의에 대한 내용이었고 이와 관련된 문제를 풀기위해서 알게된 메소드가 바로 hasNextLIne() 입니다.  
배웠던 메소드가 있는데 hasNextLine입니다.  

이 두가지 메소드를 사용하기위해서 Scanner 클래스를 사용해야합니다.  

Scanner 클래스 사용은 이전에 포스팅했던 내용을 확인하면 알 수 있습니다.  
<https://legas-park.github.io/javaclass/posting/solvetest/Scanner/>  
```java
Scanner scan = new Scanner(System.in);
```
Scanner 클래스를 사용하고나서 EOF에 대한 문제를 풀기전에 알아야하는 두가지 메소드를 이해하고 넘어가야합니다.  

## 1-1 hasNextLine()
첫번쨰  
hasNextLine()은 boolean 타입의 메소드입니다.  
그럼 hasNextLine은 true or false의 두가지 값을 리턴한다는 것을 알 수 있습니다.  
하지만 해당 메소드의 정의를 보면  
다음에 읽을 수 있는 값이 있는지 없는지 확인하고 값이 있다면 true를 반환한다고 되어있습니다.  
값이 없으면 input값이 들어올때까지 기다리고 값이 있다면 true를 반환한다...  
그리고 중요한점은 키보드의 Enter(엔터) 또한 (\n)값으로 읽는다는 것입니다.  

# 2. 문제 풀이
EOF에 도달할떄까지 input의 값을 출력  


Sample Input  

Hello world  
I am a file  
Read me until end-of-file.  

Sample Output  

1 Hello world  
2 I am a file  
3 Read me until end-of-file.    

## 2-1 풀이전 생각
Scanner 클래스 사용  
System.in 메소드 활용  
hasNextLine 메소드 활용  
입력될때마다 증가하는 숫자 활용  

# 3.  문제 제출 코드
<details>
  <summary>여기를 눌러서 코드를 확인하세요</summary>
  <div markdown="1">
```java
import java.util.*;

public class SolveEOF {

    public static void main(String[] args){

        Scanner scan = new Scanner(System.in);

        int b = 1;
        while (scan.hasNextLine()){

            String a = scan.nextLine();
            System.out.println(b+" "+a);
            b+=1;

        }

    }
}
```
  </div>
</details>  
  
		
위의 문제를 풀고 코드를 제출하고나서 한번 더 작성한 코드를 봤는데 결국 항상true값이기 때문에  
끝없이 지속되어 EOF문제이구나 라고 생각했습니다.  
그렇다면 실행했던 코드를 종료시키기위해서는 강제로 종료를 할 수 밖에 없고, 그렇다면 이런 코드를 대체 어디서 사용할 수 있나 생각하면서 코드안에서 지금 코드를 빠져나갈 수 있는 코드를 새로 만들자고 생각했습니다.


그래서 사용한 메소드가 indexOf() 함수 입니다.  
indexOf()함수는 int형 타입의 함수이며 문자열 내에서 지정된 문자나 문자열이 처음 발견되는 index를 반환하는 함수입니다.  
`만약 발견되는 문자나 문자열이 없다면 -1값을 반환합니다.`  

그렇다면 지정된 문자가 발견되기 전까지는 항상 -1 값을 가지고 있다고 생각하면 되겠구나 라고 생각하면서 빠져나갈 수 있는 코드를 만들어 봤습니다.  
사용방법은  
확인할문자or문자열.indexOf(찾을 문자or문자열)
Ex)
```java
String a = "레가스";
String b = "!";
System.out.println(a.indexOf(b));
```
위처럼 예시로 사용하는 것을 보면
변수 a에서 b의 문자or문자열이 있다면 해당 index를 반환하는것 확인하는 함수입니다.
결과는 a에서 b의 문자or문자열이 없으니 -1을 반환하게됩니다.  

## 3-1 추가 코드
```java
import java.util.*;

public class SolveEOF {

    public static void main(String[] args){

        Scanner scan = new Scanner(System.in);

        int b = 1;
        String find = ".";
        while (scan.hasNextLine()){

            String a = scan.nextLine();
            System.out.println(b+" "+a);
            b+=1;

            if(a.indexOf(find)>-1){ // -1보다 크게한것은 가장 빠른 index를 반환하게 되는 값이 0부터 시작되기 때문
                System.out.println("Enough");
                break;
            }
        }

    }
}
```
이제 indexOf함수를 사용하며 지정된 문자or문자열이 나오게 되면 코드를 종료시키게 되었습니다.  
추가로 해당 함수를 배우면서 바꿀 수있는 다른 함수도 있지만 그것은 다음 포스팅에 포스팅하도록 하겠습니다.
