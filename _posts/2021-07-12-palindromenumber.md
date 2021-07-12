---
title: Leetcode 알고리즘 테스트 [Palindrome Number]
categories:
- SolveTest
- Posting
tags:
- learnjava
- Leetcode
toc_sticky: true
toc: true
---

안녕하세요 Legas 입니다 :)  
  
지난포스팅에 풀었던 Reverse Integer에 이어서 연계되는 문제인 Palindrome Number을 포스팅 하겠습니다.
  
# 1. 알고리즘 문제 Palindrome Number
정수 x가 주어졌을때 x가 회문이라면 true값을 반환하시오.  
  
Int타입의 범위는 [-2^31,  2^31 - 1]  
따라서 -2^31 <= x <= 2^31 - 1 이라고 보면 된다.  
  
문제 예시  
Input : x = 121  
Output : true  
  
문제예시 2  
Input : x = -121  
Output : false  
output값이 false인 이유는 왼쪽에서 오른쪽으로 읽을땐 -123이지만 오른쪽에서 왼쪽으로 읽게되면 121-이므로 회문숫자가 아니므로 반환값은 false이다.  
  
문제예시 3  
Input : x = 10  
Output : false  
예시 2번과 마찬가지로 회문숫자가 아니므로 반환값 false이다.  
  
문제예시 4
Input : x = -101  
Output : false  

# 2. 알고리즘 문제 풀이
이번 문제를 보고나서 생각했던건 지난번 문제의 Revers Integer의 코드를 사용하여 풀이하면 될꺼라 생각했습니다.  

첫번째는 왼쪽에서 오른쪽으로 읽을때의 숫자와 오른쪽에서 왼쪽에서 읽을때의 숫자를 생각하면 두개의 값을 검사하는 코드를 만들어야하기 때문에 처음 주어진 x값과 거꾸로된 숫자의 값을 서로 비교해서 같으면 true 틀리면 false를 반환하도록 코드를 만들어야한다고 생각했습니다.  
  
두번째는 int타입의 숫자를 거꾸로 바꾼 값을 String타입으로 변환했을때 숫자외에 다른기호나 문자가 있다면 예외상황이 발생함으로 처음 주어진 값과 비교될 값을 둘다 String타입으로 비교해야한다고 생각했습니다.  
  
반환값은 x의 값을 반환하는게 아니라서 int타입으로 비교를 하지 않아도되어서 String타입으로 비교할 수 있다고 생각했습니다.  
```java
class Solution {
    public boolean isPalindrome(int x) {
        String rev = Integer.toString(x);
        System.out.println(rev);
        char[] charArray = new char[rev.length()];
        char[] revArray = new char[rev.length()];
        int a =rev.length()-1;
        for(int i=0; i<rev.length(); i++){
            charArray[i] = (rev.charAt(i));
            revArray[a]=charArray[i];
            a--;
        }
        String revNew = String.valueOf(revArray);
        if(revNew.equals(rev)){
            System.out.println("true");
            return true;
        }else{
            System.out.println("false");
            return false;
        }
    }
}
```
# 문제 해결 방법
첫번째 예시에 -121 처럼 -부호가 붙어있는 경우에 String타입으로 변환 후 다시 Int타입으로 변환 할 수 없으니 처음부터 String타입으로 변환  
  
두번째 이전문제인 Reverse Interger에서 사용했던 거꾸로 바꾸는 코드를 사용하여 거꾸로 바꾸고나서 String타입으로 저장  
  
세번째 맨처음 주어진 x의 String타입으로 변환한 rev와 거꾸로 변환한 revNew를 서로 비교했을때 ture면 true값을 반환 false면 fasle값을 반환하도록 코드 완성!
  
다음 문제를 풀고나서 이어서 포스팅하도록 하겠습니다. :)
