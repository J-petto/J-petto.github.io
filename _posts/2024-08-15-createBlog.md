---
title: Jekyll Github 블로그 만들기
date: 2024-08-14 13:23:00 +/-0800
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

```shell
rbenv install -l
rbenv install 3.3.4

//설치한 ruby 버전 확인
rbenv version
* system
  3.3.4
```