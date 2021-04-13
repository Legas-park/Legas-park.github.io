---
title: Initializer Block(초기화 블록)
tags:
- learnjava
- beginner
- HackerRank
categories:
- Javaclass
- SolveTest
toc: true
toc_sticky: true
---

안녕하세요 Legas 입니다. :)

이번 포스팅은 초기화 블록에 대한 포스팅을 하도록 하겠습니다.  
지난번 풀었던 EOF다음 문제로 초기화 블록에 대해서 풀고나서 공부하고 이해한 내용으로   
포스팅을 시작하도록 하겠습니다.  

# 1. Initializer Block(초기화 블록)
초기화 블록이란 클래스가 생성될때 무조건 실행되는 블록을 의미합니다.  
초기화 블록에는 두가지 종류가 있습니다.  
클래스 초기화 / 인스턴스 초기화인 2가지 종류로 되어있습니다.  

## 1-1. 클래스 초기화
클래스초기화는 클래스가 생성될때 `한번`만 실행되는 블록을 의미합니다.  
자바를 공부하게되면 클래스가 무었인지 메소드가 무었인지 자연스럽게 알게되며 이 내용을 잘 알고있어야 이제부터 공부에 대한 이해가 잘 될것이라 생각됩니다.  
## 1-2. 인스턴스 초기화
인스턴스 초기화는 클래스초기화와 달리 객체가 생성될떄마다 실행시키는 블록을 의미합니다.  
이 과정을 이해하기 쉽게 예시를 만들어봤습니다.  

### 초기화블록 예시
메인메소드가 작동하는 클래스에서 다른클래스의 초기화블록을 이용하면서 이해하는 과정입니다.  
#### Item클래스 생성
```java
public class Item {
    String name;
    int dmg;
    String effect;
    String effect1;
    String skill;
    String skill1;

    static { // 클래스 초기화
        System.out.println("===== 아이템 정보를 확인합니다. =====");
    }

    String status(){ // 인스턴스 초기화
        String item = "아이템의 이름은:"+name +"이고"+ " 데미지는: "+dmg+"이고 "+effect+" 효과가 있습니다.";
        System.out.println("===== 아이템 정보를 불러오는 중입니다.... ... .. . =====");
        return item;

    }
}
```
우선 Item이라는 클래스를 만들어서 Item에 대한 효과와 설명등을 선언합니다.  
변수선언 아래 클래스 초기화부분에 처음 클래스를 생성했을때 나타내는 실행문을 넣었습니다.  
클래스초기화를 하기위해서는 특정 단어와 {} 중괄호를 이용해서 사용하는것을 클래스 초기화라고 합니다.  

그다음 인스턴스 초기화를 생성하여 Item에 대한 정보가 나올때마다 정보를 나타내는 실행문을 넣습니다.  
인스턴스 초기화를 하는 방법은 다양하게 있습니다.  
{}중괄호를 사용하게되면 인스턴스 초기화를 하게되며 위의 코드처럼 String 타입으로 초기화를 해도 문제가 없습니다.  

#### Item클래스를 사용할 메인메소드 생성
```java
public class Itemclasstest {
    public static void main(String[] args){

        Item v1 = new Item(); // Item 클래스 생성과 동시에 객체 생성
        Item v2 = new Item(); // 추가된 객체 생성

        v1.name = "무적검";
        v1.dmg = 10_100;
        v1.effect = "무조건 한방";

        v2.name = "무적방패";
        v2.dmg = 10_100;
        v2.effect = "무적";

        System.out.println(v1.status());
        System.out.println();
        System.out.println(v2.status());
        System.out.println();
        System.out.println("어드민님 환영합니다.");


    }
}
```
이제 메인메소드가 있는 코드를 실행하게되면 Item클래스에서 사용한 클래스초기화와 인스턴스 초기화가 실행될것입니다.  
처음 클래스를 생성하면서 동시에 객체를 생성했으니 클래스 초기화블록이 1번째로 실행.  
동시에 객체를 생성했으니 인스턴스 초기화 블록이 2번째로 실행, 추가로 객채를 생성했으니 3번째로 인스턴스 초기화블록 실행.  

결과  
![]({{ 'assets/images/InitializerBlock/initializer1.JPG' | relative_url }})  
완벽합니다!  
위의 설명대로 분명 메인메소드에는 출력을 Item클래스에서 status만 출력했는데 클래스초기화 블록이 실행되는것을 볼 수 있습니다.  

초기화 블록을 사용하는것은 꼭 새로운 클래스를 생성하여 할 필요는 없습니다.
```java
public class Itemclasstest {

// 이곳에서 초기화 블록을 사용해도 됩니다.

    public static void main(String[] args){
		
		}
}
```
메인메소드가 있는곳에서 초기화 블록을 사용해도 되기 떄문입니다.

# 2. 문제풀이
무작위 정수인 공간 : B  
무작위 정수인 높이 : H  
인풋의 B와 H가 주어질때 초기화블록을 사용하여 결과 출력  

만약 B와 H의 인풋이 0보다 작거나 같을 경우 java.lang.Exception: Breadth and height must be positive 출력
B와 H의 범위는 -100<=B,H<=100.  

Sample input 1  
1  
3  

Sample output 1  
3  

Sample input 2  
-1  
2  

Sample output 2  
java.lang.Exception: Breadth and height must be positive  

```java
public class Solution {

    
public static void main(String[] args){
		if(flag){
			int area=B*H;
			System.out.print(area);
		}
		
	}//end of main

}//end of class
```
메인메소드의 변수를 참고하여 초기화블록을 사용해서 문제 풀이

# 3. 문제풀이 코드
```java
ublic class Solution {

static Scanner scan = new Scanner(System.in);
    static int B = scan.nextInt();
    static int H = scan.nextInt();
    static boolean flag = 0<B && B<=100 && 0<H && H<=100;
    static {
        if(!flag){
            System.out.println("java.lang.0Exception: Breadth and height must be positive");
        }

    }
    
public static void main(String[] args){
		if(flag){
			int area=B*H;
			System.out.print(area);
		}
		
	}//end of main

}//end of class
```

초기화 블록을 공부했지만 아직 이해하기에는 조금 부족한 실력이라 조금 더 공부가 필요할것같습니다.....  
더욱 더 공부하여 바뀌는 과정을 계속 포스팅하도록 하겠습니다.
