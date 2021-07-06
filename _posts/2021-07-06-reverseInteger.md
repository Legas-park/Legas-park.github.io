---
title: Leetcode 알고리즘 테스트 [Reverse Integer]
categories:
- SolveTest
- Posting
tags:
- learnjava
- Leetcode
toc_sticky: true
toc: true
---

안녕하세요 Legas 입니다.  
  
첫번쨰 문제를 폴고나서 다음문제 풀기까지 한참 시간이 걸렸습니다..,  
이번 문제는 제목에서 알 수 있듯이 Reverse Integer 입니다.  

그럼 바로 문제 내용과 풀었던 내용을 포스팅 하도록 하겠습니다.  


# 1. 알고리즘 문제 Reverse Integer
Int타입의 정수 x가 주어졌을때 거꾸로된 x를 return하고, 만약 x가 Int타입의 범위에서 벗어난다면 0을 return하시오.  
Int타입의 범위는 [-2^31,  2^31 - 1]  
따라서 -2^31 <= x <= 2^31 - 1 이라고 보면 된다.  

*문제 예시 1  
  
Input  x = 123
Output = 321  

*문제 예시 2  
  
Input  x = -123
Output = -321  
  
*문제예시 3
  
Input  x = 120
Output = 21
  
*문제예시 4
  
Input  x = 0
Output = 0  

위와 같은 문제 예시를 보고 해당 문제를 풀 수 있는 코드 만들기  
# 2. 알고리즘 문제 풀이
이 문제를 보고 처음에 필요하다고 생각했던 건 숫자를 > 문자열 > 배열 순으로 바꾸는 것을 생각했습니다.  
두번째는 배열에 저장된 숫자들을 거꾸로 바꾸기위해 for문을 사용해야된다 라고 생각했습니다.  

아래 문제풀이
```java
public int reverse(int x) {
        long z = x;
        boolean intRange = z<=(int)Math.pow(-2,31) || z>=(int)Math.pow(2,31)-1;
        if (!intRange) {
            if(x%10==0){
                x=x/10;
            }
        } else {
            return 0;
        }
        String rev = Integer.toString(Math.abs(x));
        System.out.println(rev); // String 타입으로 제대로 변환된건지 확인
        char[] charArray = new char[rev.length()];
        char[] revArray = new char[rev.length()];
        int a =rev.length()-1;
        for(int i=0; i<rev.length(); i++){
            charArray[i] = (rev.charAt(i));
            revArray[a]=charArray[i];
            a--;
        }
        String revNew = String.valueOf(revArray);
        System.out.println(revNew); // "revNew"
        z=Long.parseLong(revNew);
        boolean intRange2 = z<=(int)Math.pow(-2,31) || z>=(int)Math.pow(2,31)-1;
        if(intRange2){
            return 0;
        }else {
            if(x<0){
                x=Integer.parseInt("-"+revNew);
            }else{
                x= Integer.parseInt(revNew);
            }
            System.out.println(x);
            return x;
        }
    }
```
# 문제 해결 방법
첫번째 시작은 Int타입 범위 외의 숫자가 Input x 로 사용될 경우 해당 숫자를 처리하지않고 0으로 return하기 위해  		검사해야하는 if문을 사용하여 시작했습니다.  
  
두번째 예시중 120이란 숫자가 주어졌을때 0을 뺀 나머지를 거꾸로하는데 0을 빼기위해서는 10으로 나눠 코드 실행  
  
세번째 Int타입의 숫자를 String 타입으로 변환하면서 -숫자(음수)가 주어졌을때 절대값을 적용시켜서 양수로 바꿈  
  
네번째 숫자는 랜덤으로 주어지기때문에 숫자의 길이만큼 배열을 2개 만듬  
배열 1은 String타입의 문자를 하나씩 배열에 저장하기 위함  
배열 2는 배열1에 저장된 문자를 거꾸로 다시 배열에 저장해야하므로 2개의 배열 생성  
  
다섯번째 for문을 사용하여 String타입의 변수 rev를 charAt()를 사용하여 배열 1에 문자 한개씩 저장하고  
저장한 문자를 거꾸로 배열 2에 다시 저장  
이때 배열 1은 rev문자 0번쨰부터 순서대로 저장해서 ex)1,2,3씩 저장된다면  
배열 2는 배열 1에 저장된 1,2,3이 배열 끝자리부터 순서대로 저장  
배열 2의 index 2에 1이 저장되고, index 1에 2가 저장되고 index 0에 1이 저장되면서  
배열 2를 본다면 [3][2][1]로 저장되게끔 for문을 사용!  
  
여섯번째 거꾸로 잘 저장된 배열 2를 다시 문자열로 변환 String 변수 = String.valueOf(); 사용  
  
일곱번째 처음 주어진 숫자를 > 문자 > 배열 > 뒤집기 > 문자로 바꿧으니 다시 숫자로 변환하면서 int타입 범위 검사  
  
여덟번째 검사에 문제가 없을경우 만약 처음 주어진 x가 음수였을경우 변수 revNew를 숫자로 변환하면서 앞에 문자"-"붙임  
만약 음수가 아닐경우 그대로 int타입으로 변환하면서 결과값 반환  
  
이렇게 첫번째 알고리즘 문제 포스팅을 하면서 두번째 알고리즘 문제를 풀기까지 시간이 많이 흘렀지만  
문제를 보고 다른 해답을 참고하지 않고 내 방식으로 내 코드를 만들어서 풀고 있다보니 풀이가 늦어지고  
더 많이 배우고 노력해야한다는것을 깨닫게 됩니다.  
  
앞으로도 더 공부해서 계속 지속적으로 발전되는 모습을 기록하면서 이번 포스팅 마치겠습니다.  
감사합니다!
