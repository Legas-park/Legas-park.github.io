---
title: Java for loops
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

제 기준에서 정말 어렵고 어려웠던 for문 문제를 풀고나서 포스팅을 하게 되었습니다.

바로 설명과 포스팅 시작하겠습니다.

# 1.For문으로 숫자 둘러싸기
1부터 100사이의 n숫자가 주어졌을때 다음과 같이 나타낼 수 있게 코드를 만들기  

Sample Input  
2

Sample Output  
4 4 4 4 4 4 4  
4 3 3 3 3 3 4  
4 3 2 2 2 3 4  
4 3 2 1 2 3 4  
4 3 3 3 3 3 4  
4 4 4 4 4 4 4   

Sample Input  
7  

Sample Output  
7 7 7 7 7 7 7 7 7 7 7 7 7   
7 6 6 6 6 6 6 6 6 6 6 6 7   
7 6 5 5 5 5 5 5 5 5 5 6 7   
7 6 5 4 4 4 4 4 4 4 5 6 7   
7 6 5 4 3 3 3 3 3 4 5 6 7   
7 6 5 4 3 2 2 2 3 4 5 6 7   
7 6 5 4 3 2 1 2 3 4 5 6 7   
7 6 5 4 3 2 2 2 3 4 5 6 7   
7 6 5 4 3 3 3 3 3 4 5 6 7   
7 6 5 4 4 4 4 4 4 4 5 6 7   
7 6 5 5 5 5 5 5 5 5 5 6 7   
7 6 6 6 6 6 6 6 6 6 6 6 7   
7 7 7 7 7 7 7 7 7 7 7 7 7  

## 1-1. 문제 풀이 준비
위처럼 코드를 만들기위해서 생각했면 것을 먼저 정리하고 시작했습니다.  
1. N의 숫자를 넣어야하니 Scanner class를 사용하기  
2. for문이 한개에 행 or 열을 만들 수 있다  
3. for문 2개 중첩하여 행, 열 만들기  

여기까지 생각하고 문제를 풀기 시작했습니다.

## 1-2. 문제 풀기 시작
### 첫번째 코드
<details>
  <summary>첫번째 코드 펼치기</summary>
  <div markdown="1">
```java
public static void main(String[] args) {
        Scanner star = new Scanner(System.in);
        int n = star.nextInt();
        int x = n;
        int y = 1;
        int z = 0;
        int q = 2*n-1;
        for(z = 0; z < q; z++){
            System.out.print(n);
        }
        System.out.println();
        for(z = 0; z<q-1; z++){
            System.out.print(n);
            for(z = 0; z< q-2; z++){
                System.out.print(n-1);
            }
            System.out.print(n);
        }
        System.out.println();
        for(z = 0; z < q-1; z++){ //7
            System.out.print(n);
            for(z = 0; z < q-2; z++){//6
                System.out.print(n-1);
                for(z = 1; z < q-3; z++){//5
                    System.out.print(n-2);
                }
            }
        }
        System.out.print(n-1);
        System.out.println(n);

        for(z = 0; z < q-1; z++){ //7
            System.out.print(n);
            for(z = 0; z < q-2; z++){//6
                System.out.print(n-1);
                for(z = 1; z < q-3; z++){//5
                    System.out.print(n-2);
                    for(z = 2; z < q-4; z++){
                        System.out.print(n-3);
                    }
                }
            }
        }
        System.out.print(n-2);
        System.out.print(n-1);
        System.out.println(n);
//중앙
        System.out.print(n);
        for (z = 0; z < n; z++) {
            x = x-1;
            if(x<1){
                for(z = 0; z < n-1; z++){
                    y = y+1;
                    System.out.print(y);
                }
            }else {
                System.out.print(x);
            }

        }
        System.out.println();
//중앙
        for(z = 0; z < q-1; z++){ //7
            System.out.print(n);
            for(z = 0; z < q-2; z++){//6
                System.out.print(n-1);
                for(z = 1; z < q-3; z++){//5
                    System.out.print(n-2);
                    for(z = 2; z < q-4; z++){
                        System.out.print(n-3);
                    }
                }
            }
        }
        System.out.print(n-2);
        System.out.print(n-1);
        System.out.println(n);

        for(z = 0; z<q-1; z++){
            System.out.print(n);
            for(z = 0; z< q-2; z++){
                System.out.print(n-1);
                for(z = 1; z< q-3; z++){
                    System.out.print(n-2);
                }
            }
        }
        System.out.print(n-1);
        System.out.println(n);

        for(z = 0; z<q-1; z++){
            System.out.print(n);
            for(z = 0; z< q-2; z++){
                System.out.print(n-1);
            }
            System.out.print(n);
        }
        System.out.println();

        for(z = 0; z < q-1; z++){
            System.out.print(n);
        }
        System.out.println(n);


    }		
```
  </div>
</details>
													 		
코드 실행 결과  
![]({{ 'assets/images/for loops/for1.JPG' | relative_url }})  
수많은 for문이 보이지만 실행결과로는 문제를 푼것으로 보이지만....  
![]({{ 'assets/images/for loops/for2.JPG' | relative_url }})  
다른숫자를 넣게되면 제대로 실행이 안된다....  
		
그래도 어떻게든 한 숫자를 사용하여 정답을 만들었기 때문에 그것을 응용하면 무작위 N의 숫자가 들어가더라도 풀 수 있지 않을까 생각했습니다.
		
너무나 안일한 생각이었습니다......... 이 문제를 푼지 아마 한달 하고 더 걸렸습니다.....ㅠㅠ
		
### 두번째 코드  
<details>
  <summary>두번째 코드 펼치기</summary>
  <div markdown="1">
```java
public static void main(String[] args) {
        Scanner star = new Scanner(System.in);
        int n = star.nextInt();
        int x = 2*n-1;
        int z = 2*n-2;
        int y = 2*n-3;
        int n1 = n-1;
        for(int i=0;i<x;i++){
            System.out.print(n);
            for(int j=0;j<y;j++){
                if(i==n-1){
                    System.out.print(n1);
                    if(j>=y/2){
                        n1+=1;
                    }else{
                        n1-=1;
                    }
                }else if(0<i&i<n-1){
                    if(7<i&i<n-1){
                        if(6<j&j<y-7){
                            System.out.print(n-8);
                        }else if(5<j&j<y-6){
                            System.out.print(n-7);
                        }else if(4<j&j<y-5){
                            System.out.print(n-6);
                        }else if(3<j&j<y-4){
                            System.out.print(n-5);
                        }else if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(6<i&i<n-1){
                        if(5<j&j<y-6){
                            System.out.print(n-7);
                        }else if(4<j&j<y-5){
                            System.out.print(n-6);
                        }else if(3<j&j<y-4){
                            System.out.print(n-5);
                        }else if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(5<i&i<n-1){
                        if(4<j&j<y-5){
                            System.out.print(n-6);
                        }else if(3<j&j<y-4){
                            System.out.print(n-5);
                        }else if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(4<i&i<n-1){
                        if(3<j&j<y-4){
                            System.out.print(n-5);
                        }else if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(3<i&i<n-1){
                        if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(2<i&i<n-1){
                        if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(1<i&i<n-1) {
                        if (0<j&j<y-1){
                            System.out.print(n-2);
                        } else {
                            System.out.print(n-1);
                        }
                    }else{
                        System.out.print(n-1);
                    }
                }else if(n-1<i&i<2*n-2){
                    if(n-1<i&i<2*n-8){
                        if(5<j&j<y-6){
                            System.out.print(n-7);
                        }else if(4<j&j<y-5){
                            System.out.print(n-6);
                        }else if(3<j&j<y-4){
                            System.out.print(n-5);
                        }else if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(n-1<i&i<2*n-7){
                        if(4<j&j<y-5){
                            System.out.print(n-6);
                        }else if(3<j&j<y-4){
                            System.out.print(n-5);
                        }else if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(n-1<i&i<2*n-6){
                        if(3<j&j<y-4){
                            System.out.print(n-5);
                        }else if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(n-1<i&i<2*n-5){
                        if(2<j&j<y-3){
                            System.out.print(n-4);
                        }else if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(n-1<i&i<2*n-4){
                        if(1<j&j<y-2){
                            System.out.print(n-3);
                        }else if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else if(n-1<i&i<2*n-3){
                        if(0<j&j<y-1){
                            System.out.print(n-2);
                        }else{
                            System.out.print(n-1);
                        }
                    }else{
                        System.out.print(n-1);
                    }
                }else{
                    System.out.print(n);
                }
            }
            System.out.println(n);
        }

    }
```
 </div>
</details>

두번째... 코드가 매우 깁니다...ㅠㅠ  
for문이 너무 많이 사용되기때문에 for문을 최소화하고 if문을 사용하여 문제를 풀기 시작했습니다.
이번에는 한개의 숫자만 풀수 있는것이 아닌 여러개의 숫자를 풀 수 있게 되었습니다.  

Input 6  
![]({{ 'assets/images/for loops/for3.JPG' | relative_url }})  
Input 7   
![]({{ 'assets/images/for loops/for4.JPG' | relative_url }})  
Input 10   
![]({{ 'assets/images/for loops/for5.JPG' | relative_url }})  

숫자 10을 실행했을 때처럼 제대로 작동이 안되고있고 1~9까지는 직접 if문을 계속 추가하여 어거지로 이어나가게끔 만들었습니다. 계속 if문으로 숫자를 올려가다보면 뭔가 해결책이 보일것같아서 풀었지만 역시나 문제를 푸는 접근이 잘못되었었습니다. ㅠㅠ...  
### 세번째 코드
<details>
  <summary>세번째 코드 펼치기</summary>
  <div markdown="1">
```java
public static void main(String[] args) {
        Scanner star = new Scanner(System.in);
        int n = star.nextInt();
        int x = 2*n-1;
        int z = 2*n-2;
        int y = 2*n-3;
        int n1 = n-3;
        int n11=n-3;
        int n12=n-1;
        int n2 = -n-2;
        int n3 = n-1;
        int d=n;
        int a=n;
        int a1=a+1;
        int b=2;
        int c=-1;
        int r=-1;
        int t=0;
        for(int i=0;i<x/2+1;i++){
            System.out.print(n);
            for(int j=0;j<y;j++){
                if(i==n-1){
                    System.out.print(n12);
                    if(j>=y/2){
                        n12+=1;
                    }else{
                        n12-=1;
                    }

                }else if(0<i&i<n-1){
                    if(1<i&i<n-1){
                        if(j>=z){ //z = 2*n-2
                            n2-=1;
                            System.out.print(Math.abs(n2)); //n2 = y = 2*n-3

                        }else if(j>=c){//c= -1
                            System.out.print(a);
                        }else{
                            System.out.print(n1); // n1= n-3
                            n1-=1;
                        }
                    }else{
                        System.out.print(a);
                    }

                }else{
                    System.out.print(n);
                }
            }System.out.println(n);
            a-=1;
            a1-=1;
            c+=1;
            z-=1;
            if(i<3){
                n1+=1;
                n2+=2;
            }else{ // n=6
                n1+=r;
                n2+=t;
            }
            r+=1;
            t+=1;
        }
        int n4=n-3;
        for(int q=0;q<x/2;q++){
            System.out.print(n);
            for(int w=0;w<y;w++){
                if(q<n-1){
                    if(w>=d){
                        System.out.print(n4);
                        n4+=1;
                    }else if(w<n11){
                        System.out.print(n3);
                        n3-=1;
                    }else{
                        System.out.print(b);
                    }
                }else{
                    System.out.print(n);
                }
            }
            System.out.println(n);
            b+=1;
            d+=1;
            n11-=1;
            if(q<1){
                n3+=3;
                n4-=2;
            }else{
                n4-=1;
                n3+=2;
            }
        }
    }
```
  </div>
</details>
세번째 코드는 전부 완성시키지는 않았지만 드디어 문제를 풀게 되었습니다.  
어떠한 N의 숫자를 넣게 되더라도 문제 없이 실행되게끔 코드를 만들었습니다.

Input 10  
![]({{ 'assets/images/for loops/for6.JPG' | relative_url }})  
Input 13  
![]({{ 'assets/images/for loops/for7.JPG' | relative_url }})  

중간을 기준으로 아래 코드도 위처럼 변경하면 완성 할 수 있어서 포스팅을 먼저하게되었습니다.  

위 문제를 풀기위해서 한달동안 화면만 계속 처다보면서 문제를 풀고 실행시키고 반복하며 풀게되었습니다.  
이것보다 더 쉬운 코드를 만들 수 있게되는 날까지 계속 공부를해야겠다 라는 생각을 하게되는 문제풀이였습니다.  

### 줄어드는 숫자 문제풀기
위에 풀었던 문제는 N의 숫자가 점점 줄어들면서 감싸는 형태라면 이번에는 N의 숫자가 감싸지면서 점점 증가하는 숫자로 푼것을 포스팅 하겠습니다.  

<details>
  <summary>마지막 코드 펼치기</summary>
  <div markdown="1">
```java
public static void main(String[] args) {
        Scanner star = new Scanner(System.in);
        int n = star.nextInt();
        int x = 1-n+n;
        int x1=x+1;
        int y = x;
        int z = 2*n-1;
        int z1=2*n-2;
        int c = 2*n-3;
        int v=-1;
        int a=4;
        int s=-2;
        int a1=-1;
        int s1=0;
        for(int i=0;i<z/2+1;i++){
            System.out.print(x);
            for(int j=0;j<c;j++){
                if(i==n-1){
                    System.out.print(x1);
                    if(j>=c/2){
                        x1-=1;
                    }else{
                        x1+=1;
                    }
                }else if(0<i&i<n-1){
                    if(1<i&i<n-1){
                        if(j>=z1){
                            System.out.print(s);
                            s-=1;
                        }else if(j>=v){
                            System.out.print(y);
                        }else{
                            System.out.print(a);
                            a+=1;
                        }
                    }else{
                        System.out.print(y);
                    }
                }else{
                    System.out.print(y);
                }
            }
            System.out.println(x);
            y+=1;
            z1-=1;
            v+=1;
            if(i<3){
                a-=1;
                s+=2;
            }else{
                a-=a1;
                s+=s1;
            }
            a1+=1;
            s1+=1;
        }
        y-=2;
        for(int o=0;o<z/2;o++){
            System.out.print(x);
            for(int k=0;k<c;k++){
                System.out.print(y);
            }
            System.out.println(x);
            y-=1;
        }
    }
```
  </div>
</details>

마지막 문제를 풀었던 코드를 조금 변형하니 충분히 풀 수 있게 되었습니다.  
Input 6  
![]({{ 'assets/images/for loops/for8.JPG' | relative_url }})  
Input 9  
![]({{ 'assets/images/for loops/for9.JPG' | relative_url }})  

사진처럼 문제를 풀기까지 풀었던 코드를 응용하니 충분히 풀어지게 되었습니다.

다음포스팅에서는 반쪽짜리 문제를 완벽하게 만든 코드와 어떻게 코딩을 하게되었는지  
어떠한 방법을 코드가 실행되는지를 포스팅하도록 하겠습니다.
