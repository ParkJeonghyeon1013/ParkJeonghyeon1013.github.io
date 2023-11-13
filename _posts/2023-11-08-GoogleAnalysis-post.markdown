---
layout: post
title:  "How to add Google Analysis"
description: 깃 블로그에 구글 애널리틱스 적용하는 방법 A to Z
date:   2023-11-08 09:03:36 +9
categories: Git Blog
---

### <span style = 'background-color:#fff5b1'>Google Analysis</span> 적용할 테마는 <span style = 'background-color:#fff5b1'>Texutre</span>

**1. Google analysis 계정 생성**<br>
- [Google Analytics 웹사이트](https://analytics.google.com/analytics/web/)로 들어가 계정 생성 혹은 로그인 <br>
![가입하기](/image/post_231108/signup.png)


**2. 측정 시작 버튼 클릭해서 분석할 사이트에 대한 속성을 설정해준다**<br>
- 속성 설정 시 보고 시간대나 통화를 본인 국가에 맞춰 설정해주자!
![속성설정](/image/post_231108/processing.png)


**3. 직접 설치를 클릭하면 나오는 코드를 복사해 footer.html 파일에 붙여넣기**<br>
- texture theme의 경우 footer 파일에 이미 개발자가 만들어준 analysis 탭이 따로 있다!<br>
따라서, 기존 코드를 수정하거나 그냥 복붙해서 바꿔주면 된다
![asyncCode](/image/post_231108/anc.png)
![footer](/image/post_231108/footer.png)

**4. _config.yml 파일의 analytics_id를 내 측정 ID로 수정**<br>
- footer.html과 _config.yml이 연결되어있기 때문
```html
texture에 
  analytics_id: [내 측정 ID]
```

![추적아이디](/image/post_231108/checkID.png)
![config](/image/post_231108/config.png)

**5. add - commit - push**<br>
웹 서버에 올려주기

**6. 데이터 스트림 설정에서 스트림 이름에 내 측정 ID 넣어주기**<br>
- 향상된 측정 무조건 활성화한 상태로 스트림 만들기 버튼 클릭
![데이터스트림설정](/image/post_231108/upcheck.png)

**7. Google Analysis 에 들어가면 내 블로그 방문자, 방문자 행동 분석 통계가 뜬다**<br>
시간 좀 지나 깃서버에 올라가면 뜸..
