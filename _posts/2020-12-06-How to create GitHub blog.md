---
author_profile: true
sidebar:
  nav: "How to start"
title: How to create GitHub blog(깃허브 블로그 만들기)
tags:
- blog
- GitHubblog
- beginner
categories:
- Createblog
toc: true
toc_sticky: true
---

# 깃허브에서 블로그를 만들기 

안녕하세요 Legas입니다.😊  

포스팅에 앞서 시작은 개발을 하나도 배우거나 공부하지 않은 0부터 시작하는 단계부터 실패와 해결을 찾으면서 이 블로그에 꾸준히 올릴 생각으로 시작했습니다.  

개발은 그저 나와는 먼 얘기처럼 항상 내가 배운 전공을 찾아서 일을 하다가 직업을 전향하기 시작하고부터 배우면서 아무것도 모르는 제가 당황하고 실패한 내용을 기록하여 누구나 따라 할 수 있게 하려고 글을 적습니다.  


왜 깃허브인가?
사실 가족중에 개발은 아니지만 IT쪽에 관련하여 일을 하는 형제가 있습니다.
개발을 배우려고 시작할때 블로그를 만들어 공부해왔던 것을 기록하면서 배우면 좋겠다 라고 알려주고, 알려준 블로그가 바로 Github 입니다.
사실 시작은 Github가 어떤곳이고 왜 Github인지 모르고 시작했고 나중에 깃에 대한 내용을 찾아 정리해서 올리겠습니다.

## 1.깃허브 셋팅

처음 이런 블로그를 만들기위해서는 깃허브에 가입을 해야합니다.
가입은 아주 간단합니다.

### 1-1.깃허브에 접속( github.com ) 하여 sign up을 통해 가입

![]({{ 'assets/images/Post1/img1.jpg' | relative_url }})

### 1-2.가입된 아이디로 New Repositories 생성

![]({{ 'assets/images/Post1/img2.jpg' | relative_url }})

![]({{ 'assets/images/Post1/img3.jpg' | relative_url }})


   >생성할땐 이미지의 체크버튼을 확인하고 생성버튼 클릭

### 1-3.생성된 Repositories에 Code부분쪽 누른 후 HTTPS 복사

![]({{ 'assets/images/Post1/img4.jpg' | relative_url }})

### 1-4.Github desktop 설치

![]({{ 'assets/images/Post1/img5.jpg' | relative_url }})

> 다운로드 설치 후 실행

### 1-5.깃허브 클론실행
* Github desktop에서 File >  Clone a repository > 위에서 복사한 HTTPS붙여넣기 > 아래 원하는 저장폴더 지정 > Clone 선택

![]({{ 'assets/images/Post1/img6.jpg' | relative_url }})
>Clone을 실행했다면 이제 지정한 폴더에 클론된 로컬파일이 생성됩니다.

### 1-6.깃허브 페이지 확인
* 다시 Github로 돌아가서 Settings > 아래 메뉴에서 GitHub Pages에 자신의 주소가 생겼습니다.

![]({{ 'assets/images/Post1/img7.jpg' | relative_url }})
![]({{ 'assets/images/Post1/img8.jpg' | relative_url }})

>생성된 주소는 이제 새로운 테마를 적용하며 조금씩 수정할 예정!

## 2.블로그에 테마(스킨) 적용하기
<https://github.com/mmistakes/minimal-mistakes> 제 페이지의 테마는 이것으로 적용했고, 다른 테마는 적용해보지 않아 해당 테마로 설명드리겠습니다.

* mmistakes의 Github에서 Code 메뉴 > Download ZIP 클릭 > 클론해서 로컬파일 생성했던 폴더에 압축해제

![]({{ 'assets/images/Post1/img9.jpg' | relative_url }})

### 2-1.Gitdesk top 의 Git push 활용!
컴퓨터의 로컬폴더에 압축을해제했지만 Github에서는 아무런 파일 변화가 없습니다.
위에서 설치했던 Github desktop으로 들어가면 Changes에 많은 변화가 있을겁니다.

![]({{ 'assets/images/Post1/img10.jpg' | relative_url }})

![]({{ 'assets/images/Post1/img11.jpg' | relative_url }})
>내 컴퓨터에만 설치된 내용을 이제 Github에 적용시키기 위해서는 Git push라는 것을 실행해야합니다.
Summary(왜 변경했는지의 제목) 작성 > Description(변경했던 내용들) 을 작성 후 !!Commit to main!! 버튼을 꼭 눌러야만 푸쉬가 가능합니다. 


### 2-2.개발 환경 셋팅
개발 환경이라고 해봤자 아직 아무것도 모르는 저에겐 그저 인터넷의 다른 블로그를 따라하는 방법밖에 없었습니다.
내 컴퓨터의 로컬 개발 환경셋팅을 하기위해서는 Rubby라는 것을 설치해야합니다.
<https://rubyinstaller.org/downloads/> 이곳에서 Rubby를 다운받고 Clone된 로컬파일로 이동합니다.(여기서 테마를 압축했던 폴더로 꼭 가야합니다.)

#### Rubby셋팅
해당 로컬폴더의 주소창에 cmd를 입력후 엔터 > 명령창에 아래의 명령어를 순서대로 입력
![]({{ 'assets/images/Post1/img12.jpg' | relative_url }})
![]({{ 'assets/images/Post1/img13.jpg' | relative_url }})

```
gem install bundler > bundle > jekyll serve
```
모든 과정을 순서대로 했다면 jekyll serve에 접속이 되었다고 뜹니다.

테마가 적용된것을 확인하기위해 깃허브에서 확인했던 주소 혹은 <http://localhost:4000/>  주소로 들어가면 처음 빈페이지와 달리 테마가 적용된것을 볼 수 있습니다.

##### 개발환경 셋팅 후 jekyll serve에 접속중 문제되었던 내용들 #1
```
1. ERROR `/assets/main.css’ not found with a new jekyll site
2. 모든 파일이 정렬이 안된상태로 보여 웹상에서 우클릭 > 검사 > 콘솔창에 있는 여러 에러를 발견
3. 에러내용을 그대로 구글링
4. https://talk.jekyllrb.com/t/error-assets-main-css-not-found-with-a-new-jekyll-site/797/2
5. 구글링 결과 cmd창에서 명령어 실행 후 재접
6. 해결 명령어 : gem uninstall > bundle update > gem install bundler > bundle > bundle exec jekyll serve
```

##### 개발환경 셋팅 후 jekyll serve에 접속중 문제되었던 내용들 #2
```
1. 루비 3.0(최신버전)설치 후 cannot load such file -- webrick (LoadError) 에러
2. cmd창에서 해당 에러문구 발생
3. 에러내용을 구글링
4. https://github.com/jekyll/jekyll/issues/8523
5. 해결 명령어 : bundle add webrick > bundle > jekyll serve

* 위의 에러들은 수많은 지움과 클론 반복을 통해서 나온 에러들중 그대로 진행했을때 문제가 생겼던 부분만을 작성했습니다.
* 제 GitHub에 보시면 Hello again... 은 수많은 실패를 거쳐서 만들어진 n번째 깃허브 입니다 :).
```

### 2-3.테마 셋팅
다시 로컬폴더로 들어가 필요없는 파일들 (Example 로 된 파일)을 지운 후 다시한번 Git push하기.


`로컬폴더의 폴더와 파일을 아래의 파일명과 똑같은 것들을 지우기`
```
- github
- test
- .editorconfig
- .gitattributes
- .travis.yml
- CHANGELOG.md
- docs( 샘플 파일들이 들어가 있는  폴더로 우선 나중을 위해 다른 곳으로 옮겨줍니다. )
```

#### 커스텀 수정
* 바뀐 테마 내용들을 확인
테마가 적용된 페이지를 보면 여러가지 본인의 정보와 스타일로 변경해야됩니다.


* 커스텀 수정
나의 페이지를 만들기위해서 몇가지 정보를 바꿔야합니다.
프로필등 필요한 정보를 내 정보로 바꾸기위해서는 로컬폴더의 _config.yml파일의 내용을 수정 후 업데이트를 해주면 나만의 페이지로  바뀔것입니다.


먼저 파일의 수정을 위해서는 에디터가 필요한데 저는 에디터를 Visual Studio Code 앱을 사용하여 수정했습니다.
물론 에디터 기능이 있는 다른 앱들도 있지만 Visual Studio Code가 메모리를 적게 사용한다고 찾아보고 사용했습니다.


에디터를 설치했다면 config.yml파일을 Visual Studio Code 열어서 아래의 제 config파일과 맞게 설정해주시면 됩니다.
<https://github.com/Legas-park/Legas-park.github.io/blob/main/_config.yml>

#### navigation 설정
Categories, Tag, About이 노출되기 위해서 3개의 파일을 수정해야합니다.

#### 1번 파일은 data폴더의 /navigation.yml수정
[](http://github.com/Legas-park/Legas-park.github.io/blob/main/_data/navigation.yml)

#### 2번 파일은 pages폴더의 /md 수정
[](http://github.com/Legas-park/Legas-park.github.io/tree/main/_pages)
categories, about을 아래의 이미지처럼 설정
![]({{ 'assets/images/Post1/img14.jpg' | relative_url }})
![]({{ 'assets/images/Post1/img15.jpg' | relative_url }})

####  3번 파일은 로컬폴더의 config.yml 수정
하단 defaults: 부분에 pages 부분을 추가합니다.
[](http://github.com/Legas-park/Legas-park.github.io/blob/main/_config.yml)
![]({{ 'assets/images/Post1/img16.jpg' | relative_url }})

#### 이후 필요한 설정을 위해서 아래와 같이 진행
Node.js설치하기 <https://nodejs.org/en/>

#### Node.js설치 후 package.json 수정
[](http://github.com/Legas-park/Legas-park.github.io/blob/main/package.json)
- devDependencies 안에 깃과 같이 내용 추가
- scripts에 하단에 깃과 같이 내용 추가
- 이부분은 아직  모르는 내용이지만 추후 공부하여 업데이트 하겠습니다.

#### cmd창에서 명령어 실행하기
```
1. # npm install 
(개발시)
2. # npm run watchDev:js 
(배포시)
3. # npm run build:js
```

### 2-4.Admin 셋팅
에디터 앱을 사용하여 md파일을 수정하여 블로그에 포스트를 할 수 있지만
조금 더 쉬운방법으로 포스팅하기위해 어드민 권한을 부여하면 편합니다.

로컬파일의 Gemfile 코드 수정
[](http://github.com/Legas-park/Legas-park.github.io/blob/main/Gemfile)
이후 cmd창에서 명령어 실행
명령어 : bundle install > jekyll serve

이제 <http://localhost:4000/admin/> 주소로 들어가면 어드민으로 접근이 가능합니다.
포스팅을 쉽게 작성하고 수정할 수 있게 되었습니다.(박수):)
![]({{ 'assets/images/Post1/img17.jpg' | relative_url }})

포스팅 방법은 다음 포스팅에 이어서 작성하겠습니다.
봐주셔서 감사합니다.

설명했던 부분에서 틀린부분이나 아니면 블로그를 만들면서 에러가 난 부분이 있다면 서로 공유하면서 공부하게 될 수 있으면 좋겠습니다.  :)
