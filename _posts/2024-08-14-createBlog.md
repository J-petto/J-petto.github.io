---
title: Jekyll Github 블로그 만들기
date: 2024-08-14 13:23:00 +0900
categories: [블로그 제작기]
tags: [시작]     # TAG names should always be lowercase
description: Jekyll를 이용하여 Github 블로그를 만들어 보자
media_subpath: /assets/img/post/1/
---

Jekyll을 이용해서 Github 블로그를 만들었다.   
잊어버리기 전에 글쓰기 연습 겸 정리를 해두려고 한다.   

## 1. Ruby 다운로드 받기
Jekyll는 기본적으로 ruby를 다운 받아야 사용 할 수 있다.
```shell
brew install rbenv
```
{: .nolineno }
을 입력해 ruby를 다운로드 받을 수 있는 인스톨러를 다운한다.   
그리고 .zshrc 파일을 열어 해당 코드를 추가해준다.
```shell
[[ -d ~/.rbenv  ]] && \
  export PATH=${HOME}/.rbenv/bin:${PATH} && \
```
{: .nolineno }
이로써 rbenv를 사용할 수 있는 준비가 완료되었다.   
<br>

```shell
rbenv install -l
rbenv install 3.3.4

//설치한 ruby 버전 확인
rbenv version
* system
  3.3.4
```
{: .nolineno }
설치하고 싶은 ruby 버전을 확인 후 원하는 버전을 설치해준다.  
(필자는 3.3.4 버전을 다운로드하였다.)    
마지막으로 설치된 ruby를 글로벌 or 로컬 설정해준다.   
- 글로벌 : 전역 옵션
- 로컬 : 프로젝트 별 ruby 버전 설정 옵션

```shell
// 둘 중 하나 선택하면 된다.
rbenv global 3.3.4
rbenv local 3.3.4
```
{: .nolineno }

## 2. Jekyll 다운로드 받기
이제 Jekyll을 다운로드 한다.

```shell
gem install jekyll bundler
```

## 3. 원하는 Jekyll 테마 확인하기
github.io 레포를 만들어 직접 웹페이지를 꾸밀 수 있겠지만...   
세상엔 좋은 테마들이많다.   
Jekyll에서 원하는 테마를 가져와 레포를 만들면 더 간단하게 깔끔한 블로그가 나오니 잘 이용해주자.     
Jekyll 테마를 검색해 원하는 테마를 선택한다.   
 

## 4. 테마에 맞춰 github.io 레포를 생성하기.
내가 선택한 테마는 Chirpy로 지금 이 블로그 테마이다. [Chirpy github](https://github.com/cotes2020/jekyll-theme-chirpy/)   
이 테마는 디자인도 맘에 들기도했고 wiki가 있어 설명이 잘 되어있는 편이라 편했다. [Chirpy Wiki](https://github.com/cotes2020/jekyll-theme-chirpy/wiki)   

### 1. 테마 가져오기
Chirpy는 테마를 그대로 가져와 github 레포를 만들 수 있도록 chirpy starter 레포를 제공해준다. [Chirpy starter](https://github.com/cotes2020/chirpy-starter)    
링크에 들어가 
<button style="background-color:green; border:none; border-radius:5px; color:white">**Use this template**</button> > 
<button style="background-color:white; border-color:black; border-width:0.5px; border-radius:5px; color:black">create a new repository</button> 를 선택한다.
![](img1.png)
_chirpy starter 레포_

### 2. 레포 만들기
버튼을 누르면 내 레포를 새로 만들 수 있는데 Reposiroty name에 username.github.io 입력 후 <button style="background-color:green; border:none; border-radius:5px; color:white">**Create repository**</button> 버튼을 누르면된다.
![](img2.png)
_레포 생성하기_

### 3. _config.yml 파일 수정하기
생성된 레포를 clone 해서 내 컴퓨터에 가져온 후 **_config.yml**을 변경해준다.   
```yml
// 블로그 언어 설정
lang: ko-KR 

// 블로그 시간 설정
timezone: Asia/Seoul 

// 블로그 연동 url 설정
url: "https://username.github.io" 

// 프로필 설정
avatar: 프로필 파일경로 
```
{: .nolineno }
이정도의 기본 설정을 거치고 나면 그럴싸한 나만의 github 블로그가 생기게된다.   

### \+ 추가사항 : favicon 설정하기
Chirpy에서 여기서 파비콘 만드세요~ 하는 사이트가 있는데 다른 사이트에서도 실험해본 결과로는 큰 상관은 없었다.
이미지 파일을 파비콘으로 변경 후 다운로드 한 폴더에서 json 파일과 xml 파일을 지우고 해당 폴더 이름을 favicons로 바꿔 assets/img/에 폴더를 위치시키면된다.   
![](img3.png){: .left}
<br><br><br><br><br>

이렇게 파비콘 폴더를 위치 시키게 되면 Tab 한 켠에 위치한 조그마한 이미지가 노출되게된다.
![](img4.png){: .left}   
<br><br>
다음 글에선 이렇게 만든 블로그에 글을 쓰는 방법에 대해 기록하려한다.