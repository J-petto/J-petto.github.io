---
title: Jekyll Github 블로그 만들기
date: 2024-08-14 13:23:00 +0900
categories: [블로그 제작기, 블로그 시작]
tags: [시작]     # TAG names should always be lowercase
description: Jekyll를 이용하여 Github 블로그를 만들어 보자
---

Jekyll을 이용해서 Github 블로그를 만들었다.   
잊어버리기 전에 글쓰기 연습 겸 정리를 해두려고 한다.   

### 1. Ruby 다운로드 받기
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

### 2. Jekyll 다운로드 받기
이제 Jekyll을 다운로드 한다.

```shell
gem install jekyll bundler
```

### 3. 원하는 Jekyll 테마 확인하기
github.io 레포를 만들어 직접 웹페이지를 꾸밀 수 있겠지만...   
세상엔 좋은 테마들이많다.   
Jekyll에서 원하는 테마를 가져와 레포를 만들면 더 간단하게 깔끔한 블로그가 나오니 잘 이용해주자.   
Jekyll 테마를 검색해 원하는 테마를 선택한다.   

### 4. 테마에 맞춰 github.io 레포를 생성하기.
내가 선택한 테마는 Chirpy로 지금 이 블로그 테마이다. [Chirpy github](https://github.com/cotes2020/jekyll-theme-chirpy/)   
이 테마는 디자인도 맘에 들기도했고 wiki가 있어 설명이 잘 되어있는 편이라 편했다. [Chirpy Wiki](https://github.com/cotes2020/jekyll-theme-chirpy/wiki)   

#### 1. 테마 가져오기
Chirpy는 테마를 그대로 가져와 github 레포를 만들 수 있도록 chirpy starter 레포를 제공해준다. [Chirpy starter](https://github.com/cotes2020/chirpy-starter)   
링크에 들어가 **Use this template** 선택 후 **create a new repository** 를 선택한다.