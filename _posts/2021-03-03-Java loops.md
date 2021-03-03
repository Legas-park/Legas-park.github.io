---
title: Java loops2
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

지난포스팅 이후로 이번 포스팅 텀이 길었는데 loop 문제를 풀면서 좀더 심화과정인 loop문제를 풀어보고 싶어서 찾던 도중에 해커스랭크에 있는 다른 loop문제도 도전하면서 풀기까지 아주 긴 시간이 걸려서 이제 포스팅 합니다.

반복문은 앞 포스팅처럼 여러가지 반복을 해야하는 동작을 for문을 통해서 반복시킬 수 있는데요  
단순히 반복이 아니라 반복안에서도 심화기능을 할 수 있는 것을 문제를 풀면서 배우게되었습니다.  

포스팅 시작하겠습니다.  

# 1. for문으로 별찍기
input에 n의 숫자를 넣었을때 반복하여 * 을 나타내는 문제

ex) input  
5  
ex) output  
  
![]({{ 'assets/images/loops2/img1.JPG' | relative_url }})
  
위처럼 하기위해 문제를 풀었던 코드  
```java
Scanner star = new Scanner(System.in);
    int n = star.nextInt();
    String stars = "*";
    String stars1 = "*";
        System.out.println(stars); // 처음 * 이 생성
                for (int i = 1; i < n; i++) { // 위에 *을 하나 만들었으므로 N까지 나타내기위해 i=1로 초기화
                    stars = stars + "*"; // 두번째줄에 **을 나타내기위해서 표현
                    System.out.println(stars); 

                   if (stars.length() == n/2) { // 계속 ** 두개씩 줄바꿈을 하여 출력하기에 if문 사용
                       for (int j = n/2-1; j > 0; j--) { // 의도는 남은 별을 3번만큼 for문을 사용하기위해 사용
                           for(int y = 0; y < j; y++){ // 3번 반복할때 한줄에 표현하기위해 사용
                               System.out.print(stars1); // j의 숫자 미만까지 한줄에 반복출력
                           }
                           System.out.println(); // 출력이 끝나면 줄바꿈 // 이후 다시 반복
                       }break; // 반복을 다 완료했으면 종료
                  }
        }
```
`print()`문은 기존에 사용했던 `println()`과 `printf()`이 있지만 그냥 print만 사용했을때  
줄바꿈이 없이 한줄에 길게 표시되는것을 알게되어 위처럼 사용했습니다.  

이후 계속해서 for문을 공부하다보니 위의 코드보다 훨씬 간결하고 쉽게  
output을 나타낼 수 있지만 공부하면서 사용했던 내용은 주석으로 표시했습니다.  

break을 사용하지않으면 계속 출력되기에 break로 종료시키게 되었습니다.

## 1-1 for문 공부
for문을 조금더 공부하면서 어떻게 작용되는지 알게되어서 사용했던 내용들  

기본적인 `for(int i=0; i<n; i++)` for문을 처음사용하게될때 print의 사용에 따라서
행이될 수 있고, 열이 될 수 있는걸 알게되었습니다.  
`System.out.print()`를 사용하면 한줄에 출력하게 됩니다.
`System.out.printf()`를 사용하면 한줄레 출력할 수 있거나  
지시자를 통해 출력 후 다음줄로 줄바꿈을 가능하게 해줍니다.
`System.out.println()`을 사용하면 한줄에 출력 후 다음줄로 줄바꿈을하여 출력하게 됩니다.

위의 내용대로 사용한다면 for문을 5개를 사용하면 문제의 output를 바로 표현 할 수있지만 input이 N이기 때문에
어떠한 숫자가 들어가도 점점 증가하게 만들 수 있는 for문을 만들어야 합니다.  

그러기위해서 for문을 2번 반복해서 사용하는 방법을 사용하면 좀 더 쉽게 사용할 수 있습니다.

```java
for(int i=0; i<n; i++){ // n만큼 열을 생성 아래 println()줄바꿈 기능 활용
    for(int j=0; j<=i; j++){ // 첫번째 for문이 작동되고 다음 for문에 반복될 횟수를 j<=i로 설정
		System.out.print("*"); // i=0일때 다음 for문의 j가 0이기때문에 1번 반복 다음 지속해서 i숫자만큼 반복
		}
}System.out.println();
```
위처럼 for문을 사용하게되면 첫번째 for문은 열을 생성하고 두번째 포문은 각 열마다 반복되는 행을 생성하게 됩니다.

# 2. for문으로 별찍기2
처음 문제를 풀기위해서 고민중에 for문을 사용하지만 그냥 한번에 반복해서 나타내는게 없을까 여러가지 구글링을 통해서 알아본 결과 다른방법으로 사용할 수 있는것을 확인했습니다.

아래 코드  
```java
    Scanner star = new Scanner(System.in);
    int n = star.nextInt();
    String stars = "*";
        for (int i = 1; i < n; i++) {
            String stars_power = new String(new char[i]).replace("\0", stars);
            System.out.println(stars_power);

            if (stars_power.length() == n/2) {
                for (int j = n/2-1; j > 0; j--) {
                String stars_power2 = new String(new char[j]).replace("\0", stars);
                System.out.println(stars_power2);
                }break;
           }
     }
```
` String stars_power = new String(new char[i]).replace("\0", stars);`은 지정된 i의 숫자만큼 반복하여 출력해줄 수 있는것을 확인했고 이것을 for문과 같이 사용한다면 좀더 쉽게 나타낼 수 있는것을 확인했습니다.

for문을 배우면서 결과값은 어떻게든 코드를 만들어 사용할 수 있지만 지식이 많으면 조금더 간결하고 알아보기 편하게 사용 할 수 있다는것을 알게되어 앞으로도 한가지 공부를 하더라도 그 분야에 여러가지 사용법을 배우면서 공부하는것이 좋을 거라 판단됩니다.

다음 포스팅은 for문으로 사용하는 조금 더 어려운 문제를 포스팅하도록 하겠습니다.
감사합니다 :)
