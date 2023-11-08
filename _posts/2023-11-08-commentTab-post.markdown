---
layout: post
title:  "How to add Google Analysis"
description: 깃 블로그에 구글 애널리틱스 적용하는 방법 A to Z
date:   2023-11-08 09:03:36 +9
categories: Git Blog
---

### 댓글창 적용할 테마는 <span style = 'background-color:#fff5b1'>Texutre</span>

**1. Google analysis 계정 생성**<br>
![가입하기](/image/post_231108/signup.png)

- 속성 설정 시 한국에 맞춰서
![가입하기](/image/post_231108/processing.png)

**2. 태그 안내 보기 버튼 눌러서 코드를 만든다**<br>
- 테마별로 적용 방식 다름
측정 ID를 넣어주기만 해도 되는 경우도 있음. 

**3. 코드를 footer.html에 넣어준다**<br>
![가입하기](/image/post_231108/anc.png)

**4. _config.yml 코드 수정**<br>
![가입하기](/image/post_231108/checkID.png)

**5. add - commit - push**<br>
웹 서버에 올려주기

**6. 스트림 이름에 내 측정 ID 넣어주기**<br>
- 향상된 측정 무조건 활성화 해주느 상태로 스트림 만들기 버튼 클릭하기 

조금 지나 깃서버에 올라가게 되면 내 블로그에 들어간 사용자가 몇명인지 확인할 수 있음.


<br>
texture 테마의 경우
생성된 코드를 footer.html 에 넣어줘야 함. 
개발한 사람이 미리 만들어둔게 있더라구.

하나더 해줘야 하는건 _config 들어가서 texture에 
  analytics_id: [나의 아이디]


