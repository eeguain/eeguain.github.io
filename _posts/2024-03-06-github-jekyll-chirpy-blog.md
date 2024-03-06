---
---

How to make a jekyll blog (with chirpy theme) on github pages.

Blog 글 작성방법:
github repository (code)에서 edit/new file로 블로그 글 수정/작성.
github repository에서 .을 누르면 vscode스러운 (하지만 터미널은 없는) 페이지가 열림. -> 여러 글을 동시에 수정한 뒤에 한 번에 commit하기에 좋음.

local computer로 부터 github commit을 할 수도 있음.


기본 테마의 jekyll blog 만드는 방법:
github 아이디를 만든다. (아이디에만 종속시키지 않으려면 organization까지 만든다)
repository를 만든다. (blog를 만드려는 무료 이용자라면 public으로. 이름은 깃헙아이디.github.io 혹은 organization이름.github.io)
_config.yml 파일을 만든다.


Chirpy theme으로 만드는 방법: 
local computer에서 만들어서 commit하려면 https://github.com/cotes2020/jekyll-theme-chirpy/ 을 fork한다.
(더 자세한 내용은 https://chirpy.cotes.page/posts/getting-started/ )

local 없이 browser에서만 사용한다면, 
https://github.com/cotes2020/chirpy-starter
"Sign in to GitHub and browse to Chirpy Starter, click the button Use this template > Create a new repository, and name the new repository USERNAME.github.io, where USERNAME represents your GitHub username."
https://www.youtube.com/watch?v=m1RYsmOMPLs

그리고 _config.yml의 url을 유저이름.github.io로 변경한다.

블로그 주소로 들어갔는데, index.html의 내용 그자체 

`
---
layout: home
# Index page
---
`

이게 나온다면, 해당 repository의 Settings -> Pages -> Build and deployment -> Source: Github actions로 변경.

블로그 완성.
_post 폴더에 md 파일들을 작성하면 된다.

제목은 yyyy-mm-dd-title.md

형식은
하이픈 세개
날짜, 제목 등등
하이픈 세개
내용

jekyll 블로그 사용법은 여기 비디오 리스트
https://www.youtube.com/watch?v=bDQsGdCWv4I&list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB&index=12

브라우저에서 마크다운 써보기
https://stackedit.io/
여기서 알게 됨. -> https://www.irgroup.org/posts/jekyll-chirpy/

chirpy theme 선택 이유
단순한 UI.
preindexed search (without third party like algolia) -> 이게 어떻게 가능한지는 다음에 블로그 글로 작성.


github 파일들은 cdn을 사용하면 더 빠르게 접근가능. 
github에서 자동으로 해 주는 게 있음. 예시: https://cdn.jsdelivr.net/gh/eeguain/eeguain.github.io@master/index.html 
이거는 계정의 bandwidth 사용량에 포함 안될듯? 확인 필요.
