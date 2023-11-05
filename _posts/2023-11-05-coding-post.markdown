---
layout: post
title:  "How to Make Github Blog"
description: 깃 블로그 적용하는 방법 A to Z
date:   2023-11-05 09:03:36 +9
categories: Git Blog
---

### 다음과 같은 <span style = 'background-color:#fff5b1'>순서</span>로 진행한다!

**1. 깃 블로그를 위한 기본 환경 세팅**<br>
**2. 깃 블로그 테마 적용 방법**<br>
**3. 테마 적용한 블로그 배포**<br>

---

## 1️⃣ 깃 블로그를 위한 기본 환경 세팅
**1. Git repository 생성**
레포지토리를 생성할 때 레퍼지토리명은 `[사용자명].github.io`으로 해준다!

![create repository](/image/post_231105/process_1.png)
<br>

**2. Ruby 설치**
Window OS 사용하기에 [RubyInstaller](https://rubyinstaller.org/downloads/)로 들어간다. <br>

![download Ruby](/image/post_231105/process_2.png)
<center>32비트의 Jekyll 특성상 `x86버전`으로 다운받을 것!</center>
<br>

**3. 생성된 git repository를 clone** <br>
```sh
git config --global user.name [이름]
git config --global user.email [이메일 주소]
``` 
git의 기본적인 세팅은 해줬다는 전제 하에 clone을 해오자!
<br>

git clone은 원격 레퍼지토리를 로컬 저장소로 가져오는 것! 
<br>
`git clone [레퍼지토리 링크]`을 통해 원격저장소를 로컬저장소에 복제해온다!
<br>

**4. 관리자 권한으로 Start Command Prompt with Ruby 열기**<br>
인스톨러가 이끄는대로 enter enter 누르면서 Ruby 다운로드 완료하기!
<br>
Ruby command 창을 사용할 때는 항상 **관리자 권한**으로 열어 사용하자!
<br>
여기까지 세팅해두고 원하는 테마를 찾으러 가보자!

---

## 2️⃣ 깃 블로그 테마 적용 방법
**1. 맘에 드는 jekyll 테마를 찾아 다운받자**
- jekyll Themes 사이트 하단 사이트를 통해 원하는 테마를 고른 후 파일을 다운받는다!
<br>
    [Jekyll Themes](http://jekyllthemes.org/) <br>
    [Jekyll](https://jamstackthemes.dev/ssg/jekyll/)<br><br>
<br>

![downloadTheme](/image/post_231105/textureDown.png)
<center>DownLoad 클릭하기!</center>

비주얼만으로 테마를 고르던 중 마음에 드는 테마는 [hard 테마](https://github.com/sunbliss/photorama) 였으나, 세팅이 너무 어려웠다💢
<br>
따라서, 그나마 쉬워보였던 테마인 [texture 테마](http://jekyllthemes.org/themes/Texture-Theme/)로 블로그를 세팅했다.<br>
~~그치만 texture 테마 역시 배포 시 많은 시행착오가 있었음;;~~
<br> 

**2. 다운받은 theme 파일 압축풀기**
![zip](/image/post_231105/zipFile.png)
<center>clone을 통해 생성된 로컬 디렉토리에 theme 파일 압축을 푼다!</center>

**3. _config.yml 파일 수정**
- 기존에 입력되어있던 `baseurl: /texture` 지우기
- `theme: texture` 입력
- 저장


**4. .gitignore 파일 수정**
- `Gemfile.lock`이 포함되어있나 확인!
- 혹시 몰라서 처음 세팅해줄 때 *Gemfile.lock*파일을 삭제하긴 했었음. (의미있는가? 모르겠음)

README.md 파일 참고해서 하면 된다 하나, 뜻대로 되지 않음..

**5. 관리자 권한으로 Start Command Prompt with Ruby 열기**<br>
- clone한 경로로 가기!<br>
C드라이브에서 N드라이브 등 다른 디렉토리에 저장을 해뒀다면 바로 `cd E`로 하면 이동 안됨.<br><br>
`cd /`로 최상위 디렉토리로 간 후 `N:` 과 같이 해당 `[드라이브명]:` 해주면 다른 디렉토리로 변경 완료!<br> 그 다음엔 우리가 알고 있듯 `cd `통해서 경로 지정해주면 됨.<br><br>

- command prompt에 순서대로 입력해주기
`bundle`
`gem install texture`
`bundle exec jekyll serve`
<br>
- `bundle exec jekyll serve` 실행 후 뜬 server address를 복사
![server Addr](/image/post_231105/serverAddr.png)

- 복사해둔 server address를 웹 브라우저에 붙여넣기
![localWeb](/image/post_231105/local.png)
<center>서버가 잘 생성되었음을 확인할 수 있다!</center>
<br><br>

💥로컬 웹사이트를 여는데 성공했으나, 로컬 웹사이트가 업데이트되지 않고 아래와 같은 에러가 뜰 경우
![traceError](/image/post_231105/trace.png)
- `ctrl`+`c`를 눌러 서버를 종료한 후 <br>
- `jekyll serve --trace` 입력하면 다시 서버 돌아감
<br><br>

**6. _posts 폴더의 .markdown 파일 생성해 포스팅 문서 작성**
```sh
---
layout: post
title:  "How to Make Github Blog"
description: 깃 블로그 적용하는 방법 A to Z
date:   2023-11-05 09:03:36 +9
categories: Git Blog
---
```
위의 5가지 요소를 가장 윗줄에 포함한 마크다운 문서 작성<br>
처음부터 작성하기보단 `_posts` 폴더에 있는 파일을 복붙하여 수정하는게 더 편하다
<br>
💥한국 시간은 *GMT+9* 글 쓴 시간 수정 시 사용한 방법

---

## 3️⃣ 테마 적용한 블로그 배포
1. git repository setting에서 Build source를 ***Github Action***으로 변경
![setting](/image/post_231105/settings.png)

<br>

2. 드디어 add - commit - push
```sh
git add .
git commit -m  '커밋 메시지 내용'
git push origin main
```

<br><br>

❌ 에러 검색할 때 팁 아닌 팁이라면 `action`에서 빌드되지 않은 커밋(?) 클릭해서 Error message를 찾아 구글링하는 것도 방법!
![gitActions](/image/post_231105/action.png)

---


*💨결론! 답은 구글링.. 왜 해결되었는지는 모르겠으나, 계속하다보니 action에 초록불뜬거 보고 감격ㅠㅠ*

