---
title: 포스트 작성하기
date: 2024-08-15 20:08:00 +0900
categories: [블로그 제작기]
tags: [글 작성]     # TAG names should always be lowercase
description: 블로그에 글 작성하기
media_subpath: /assets/img/post/2/
---

어제는 Jekyll로 깃헙 블로그를 만드는 글을 썼다면 오늘은 좌충우돌 글 작성에 대해 써볼려고한다.   
이 글은 Chirpy라는 테마의 글 작성 방식을 설명하는 글이다. 다른 Jekyll 테마의 작성법이 동일한지는 모르겠다...   

## 1. md 파일 만들기
_posts라는 폴더에 yyyy-dd-mm-title.md로 파일을 하나 만들어 준다.    
참고로 title에 들어가는 파일 명은 해당 게시글의 주소지가 되니 너무 막 쓰진 말자   

## 2. md 파일에 글 정보를 작성해준다.
글을 작성할 때 타이틀과 날짜, 카테고리와 태그 등 다양한 정보들을 글쓰기 전 추가할 수 있는데   
형식이 없다면 기본적으로 파일 이름에 있는 날짜와 타이틀을 기본으로 가져와 생성한다.   
```markdown
---
title: 포스트 작성하기
date: 2024-08-15 20:08:00 +0900
categories: [블로그 제작기, 글 작성]
tags: [글 작성]
description: 블로그에 글 작성하기
media_subpath: /파일경로/
---
```
{: .nolineno }

### title
title은 게시글의 제목이다. title에 작성한대로 게시글 카드에 제목이 노출된다.   
### date
date는 작성 날짜를 의미한다. yyyy-dd-MM hh:mm:ss +/-0000으로 기입한다.   
여기서 +/-0000에는 그리니치 천문대 표준시의 +/- 시차를 작성하면된다. (한국은 +0900으로 입력해주면된다.)   
### categories
categories는 게시글의 카테고리를 입력한다.   
입력하는대로 카테고리가 생성되고 이는 해당 블로그의 카테고리에서 정리되어 노출된다.   
![](img1.png)
### tags
tags는 게시물에 태그를 추가하는 것으로 ,로 몇 개든 추가가 가능하다.   
그리고 카테고리와 동일하게 추가하는대로 블로그의 태그에 정리되어 노출된다.
![](img2.png)
### description
discription은 게시물에 대한 설명으로 미작성 시 md파일의 앞부분이 카드에 노출되는 형식으로 변경된다.
![](img3_before.png)
_description 사용 전_
![](img3_after.png)
_description 사용 후_   
게시글 카드가 훨씬 깔끔해진걸 볼 수 있다.   
### media_subpath
media_subpath는 img 파일의 앞부분 경로를 미리 작성해 둠으로써 게시글 작성에서는 img.png만 적어도 이미지를 사용할 수 있게 만들어 준다.   
### 그 외...
더 많은 포스트 정보를 작성하는 방법은 Chirpy의 wiki에 간략하게 정리가 되어있다.
[Chirpy Wiki 글쓰기 페이지](https://chirpy.cotes.page/posts/write-a-new-post/)   

## 3. md 파일 형식에 맞춰 글 작성하기
게시글은 md 파일이기 때문에 기본적인 글쓰기 방식은 거의 대부분 md의 형식에만 맞추면 크게 문제없다.   
[마크 다운 문법 사용 방법](https://gist.github.com/ihoneymon/652be052a0727ad59601)   
추가적으로 html 태그도 사용할 수 있다.   
`<br>, <button>... 등등 내부 스타일까지 작성하여 사용 가능하다`   

### 주의 사항   
게시글 작성 시 bundle localhost에서는 정상적으로 동작하는 글이 커밋만 하면 빌드 에러가 나면서 커밋이 막혀 변경되지않는 현상을 겪었다. (사실 이거 때문에 이틀동안 게시글 작성이 느려졌다.)   
> 확인 결과   
> 한 줄씩 변경하면서 확인해본 결과 http 주소의 문제였음을 알게되었다.  
> https://~ : 커밋 성공, http://~ : 커밋 실패  
> http:// 로 되어있는 주소는 보안 때문인지 빌드에서 자동적으로 막힘이 확인 되었다.   
> 링크를 작성할 때는 주소에 주의하여 작성하는 것이 좋을 듯 하다.
{: .prompt-warning }


