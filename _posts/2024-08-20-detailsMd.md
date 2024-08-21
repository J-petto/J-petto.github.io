---
title: 게시글 html 태그와 md 태그에 대해
date: 2024-08-20 20:57:00 +0900
categories: [블로그 제작기]
tags: [details, markdown]     # TAG names should always be lowercase
description: 게시글 md 파일에 드롭다운과 내부 md 태그 사용 가능하게 하기
media_subpath: /assets/post_img/4/
---

네이버 클라우드를 진행하면서 기록했던 것들을 옮기다가 이슈가 생겼다.   
그 덕에 이틀 동안 다른 글들을 못 옮기다가 이제야 해결이 되어 이슈를 기록한다.   

## 그래서 뭔 일인가요.
markdown 문법에서 직접적으로 드롭다운을 제공하는 코드는 없어서 대부분 html 태그를 통해 드롭다운을 만들게 되는데

<details markdown=1>
<summary markdown="span">드롭다운이 뭔가요</summary>
뭐 대충 이런거요

```markdown
<details>
<summary>드롭다운이 뭔가요</summary>
뭐 대충 이런거요
</details>
```
{: .nolineno}
</details>   
<br>
난 드롭다운을 애용하는 사람이기에 대부분의 정리 게시글에 한 개씩을 끼워져있다고 봐야한다.   
근데 해당 코드를 사용하게되면 대부분의 md 파일은 한 칸을 띄우면 자동적으로 html 코드와 분리되어 내부 md 코드가 정상적으로 작동된다.
```markdown
<details>
<summary>드롭다운이 뭔가요</summary>

- 내부문에서 위 아래 한칸을 띄우면 정상 작동함

</details>
```
{: .nolineno}

당연히 md 파일로 게시글을 작성하니 동일하게 동작한다고 생각했는데....

## 응 아니야
음 예상과는 다르게 내부 md 코드가 인식되지않고 그냥 텍스트로 모두 변환되어 나타나버린다.

<details>
<summary>난 띄웠는데 왜그래요</summary>

- 난 모르겠다니깐요
```markdown
코드문도 당연히 안 먹죠 그럼요
```

</details>
<br>
여러방면으로 찾아보니 Jekyll의 이슈였던 것이었다.   
[Jekyll 이슈 #9297](https://github.com/jekyll/jekyll/issues/9297)   
위 이슈에 가면 나와 같은 문제를 겪는 사람들의 고충과 해법이 정말 다양했는데   
여러가지를 시도해봤을 때 깔끔하게 사용할 수 있는 방법을 찾았다.

## 해결안
`<details>`에 markdown=1 속성을 추가해주고 `<summary>`에 markdown="span" 속성을 추가해주면 내부 md 코드가 정상적으로 돌아간다.
<details markdown=1>
<summary markdown="span">이렇게 하면되더라고요</summary>

    <details markdown=1>
    <summary markdown="span">이렇게 하면되더라고요</summary>
    내용 입력
    </details>
    
</details>
<br>
이제 다시 정리본을 옮기면 된다. 하하