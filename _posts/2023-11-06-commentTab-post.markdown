---
layout: post
title:  "How to Make Comment box by Utteranc"
description: 깃 블로그에 댓글창 만드는 방법 A to Z
date:   2023-11-06 09:03:36 +9
categories: Git Blog
---

### 댓글창을 만들 테마는 <span style = 'background-color:#fff5b1'>Texutre</span> 아래와 같은 순서로 진행

**1. Utterances 세팅**<br>
**2. 로컬 / 웹 배포 방법**<br>

---

## 1️⃣ Utterances 세팅
**1. Utterances Github app 설치**<br>
[Utterances GitHub App](https://github.com/apps/utterances) 👈클릭해서 Utterances install 페이지로 들어가 install 클릭

![utterances install button](/image/post_231106/install_u.png)
<br>

**2. Utterances 저장할 repo 범위 지정**<br>
블로그 repo에만 저장해줄거니깐 `~~~~.io` repo로 설정해줌
![select repo](/image/post_231106/select_repo.png)

**3. Blog Post <-> Issue mapping 에서 이슈 이름을 어떻게 설정할지 설정**<br>
보통 *Issue title contains page pathname*으로 해준다

**4. configuration 탭 > repo에 repo 주소 써주기**<br>
> `repo = [요기에 들어갈]` 내용인 `내아이디/홈페이지repo명`을 repo에 입력해주기! 
<br> Utterances가 생성해준 코드를 복사
```html
<script src="https://utteranc.es/client.js"
      repo="ParkJeonghyeon1013/ParkJeonghyeon1013.github.io"
      issue-term="pathname"
      theme="boxy-light"
      crossorigin="anonymous"
      async>
```

**5. 복사한 코드를 _layouts > post.html 하단에 붙여넣기**<br>
![code location](/image/post_231106/code_location.png)

## 2️⃣ 로컬 / 웹 배포 방법<br>
구체적인 서버 여는 방법은 이전 포스트 참고<br>
1. 로컬 웹서버로 적용 여부 확인<br>

```sh
bundle exec jekyll serve 

or 

jekyll serve --trace 
```

2. 로컬 웹서버 확인했으면, 웹으로 올라가도록 
`add - commit - push`
