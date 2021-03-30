---
title: How to clean post<code>
tags:
- GitHubblog
categories:
- Createblog
- Posting
toc: true
toc_sticky: true
---

안녕하세요 Legas 입니다. :)

이번 포스팅은 긴 코드를 깔끔하게 정리하기위해 마크다운 문법을 사용하는 방법을 포스팅하겠습니다.

제 포스팅에서도 사용하고있지만 가끔 엄청 긴 코드를 포스팅에 사용하는 경우가 있는데  
이때 코드들이 전부 보여서 페이지가 너무 길게 나오는것을 깔끔하게 정리하기위한 방법입니다.  

# 1.마크다운 문법으로 코드 표현
포스팅을할때 코드를 표현하기위해서는 아래와 같이 마크다운 문법을 사용해야합니다.  
제 경우는 java공부를 하고있기 때문에 코드를 적을때  

![]({{ 'assets/images/how to clearn post code/code1.JPG' | relative_url }})  

예시  
```java
Hello Legas :)
```

# 2.마크다운 문법으로 깔끔한 코드 표현
코드들은 이제 얼마든지 표현 가능하지만 긴 코드나 깔끔하게 보고싶은 코드들을 접거나 펼치기 기능을 사용하여 표현 할 수 있습니다.  
예시  
<details>
  <summary>여기를 눌러서 코드를 확인하세요</summary>
  <div markdown="1">
```java
		
Hello Legas :) 
How to make clean code
		
```
   </div>
</details>  

		
위처럼 클릭을 해서 긴 코드를 펼치기와 접기를 통해서 포스팅을 좀 더 깔끔하게 보일 수 있습니다.

코드를 작성할때 위 아래에 아래와 같은 명령어를 적어주면 표현이 가능합니다.
예시) 
```
<details>
  <summary>여기를 눌러서 코드를 확인하세요</summary>
  <div markdown="1">
		
		(코드 내용들)
		
  </div>
</details>
```

아래 포스팅시 적용한 이미지  
![]({{ 'assets/images/how to clearn post code/code2.JPG' | relative_url }})  

이제 긴 코드나 정리하고 싶은 코드들은 위와같이 적용하여 포스팅을 해보세요 :)
