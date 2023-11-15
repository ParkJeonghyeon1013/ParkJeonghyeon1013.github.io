---
layout: post
title:  "How to add Google search console manager"
description: 깃 블로그에 구글 검색에 잡히도록 만들기
date:   2023-11-9 07:00:36 +9
categories: Git Blog Google Search
---

### <span style = 'background-color:#fff5b1'>Google search console manager</span> 적용할 테마는 <span style = 'background-color:#fff5b1'>Texutre</span>

<br>

**1. Google Search Console 들어가서 로그인**<br>
- [구글 서치 콘솔 웹사이트](https://search.google.com/search-console/about)로 들어가 계정 생성 혹은 로그인 <br>

**2. URL 접두어에 자신의 블로그 주소 복붙**<br>
![url접두어](/image/post_231109/urlHead.png)

**3. 소유권 확인을 위한 코드를 add - commit - push**<br>
- 소유권 확인을 위한 코드를 생성해준다. 해당 파일을 다운받아서 로컬 저장소에 저장
- `add - commit - push`를 통해 원격 저장소에 올려줌
![소유권 확인을 위한 코드](/image/post_231109/checkMine.png)

<br>
원격 저장소에 올라간 후 얼마 지나면 구글에서 소유권이 확인되었다는 메시지를 띄워준다!
![소유권 확인](/image/post_231109/confirmMine.png)

**4. robots과 stiemap.xml 파일을 올려줌.**<br>
- 내 홈페이지에 맞는 sitemap.xml 파일을 만들어 `add - commit - push`
![robots과 sitemap 저장 경로](/image/post_231109/whereToAdd.png)

**5. 좌측 Sitemaps 탭에 들어가 sitemap.xml을 입력 후 제출해줌.**<br>
![사이트맵 추가](/image/post_231109/addSiteMap.png)
![sitemap.xml 복붙](/image/post_231109/addNewSitemap.png)

구글에서 확인하는데 시간이 걸리나 얼마 후 사이트맵이 제출되었다고 뜬다.

<br><br><br><br>

**?? 오류 해결하는 팁??**<br>
그러나, texture 테마의 경우 유효한 URL이 아니라는 에러가 발생함.. 이를 해결하는 과정은 찾아서 추후 업로드 할 예정.<br>

![sitemap.xml 에러](/image/post_231109/sitemapError.png)
오류가 발생함.
[xml 파일에서 에러를 찾아주는 사이트 링크](https://www.xml-sitemaps.com/validate-xml-sitemap.html) 
이 사이트를 통해서 오류를 해결할 수 있을 짇...도/?
