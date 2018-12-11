---
title:  "좌충우돌 Jekyll blog구축기와 Todo"
date:   2018-12-11 11:33:00 +0900
categories: Dev
---


유행은 돌고 도는 것이랬던가 남들 다 하는 SNS를 거쳐 다시 블로그로 돌아오게 되다니..

삽질은 자꾸 하게되지만 인간은 똑같은 실수를 반복하게 된다고 했던가 아무래도 삽질을 기록해두는게 좋을것같아서 블로그를 시작해야겠다는 마음을 먹게 되었고
기술적으로 대단하고 멋진 글이 올라오는 것이 아니라, 새롭게 배우는 것들, 삽질하면서 알게된 것들, 개발자로서 관심을 가지고 살펴 보다가 정리가 필요해서 정리한 것들… 이런 글들을 써야겠다는 생각이 들었다.

[우아한형제들의 Baby Steps-우아한 형제들 기술블로그](http://woowabros.github.io/woowabros/2016/06/30/woowabros_cto.html)



컴퓨터 관련내용이 주가 될텐데 이왕이면 요새 유행한다는 지킬을 써봐야겠다는 생각을 했고 에이 뭐 얼마나 어렵겠어 좀 귀찮기야 하겠지하고 덤벼들었다.

첫글이니 가벼울거라 생각하고 덤벼든 지킬 구축(삽질)기로 시작해보려 한다.

필자의 환경인 OSX를 기준으로 한다.

## local에 jekyll 설치

> \> sudo gem install jekyll bundler 

> \> jekyll new my-awesome-site

이렇게만 해도 기본적인 블로그를 하기위한 준비가 끝난다

> \> bundle exec jekyll serve

실행 후 웹브라우저로 localhost:4000 에 접속해보면 블로그를 확인할 수 있다.

git의 기본적은 사용법은 안다고 가정했을때..

github 에서 저장소 제목을 (username).github.io로 생성하고
좀전에 만든 my-awesome-site를 push하면 제일 기본적인 화면의 블로그가 나타난다

![create-github-repo]({{ site.url }}/images/create-github-repo.png
 "create github repo")

![first-main]({{ site.url }}/images/jekyll-first-main.jpg
 "jekyll default page")

첫 화면을 띄운 기쁨도 잠시..

뭐 이건 기능도없고 이쁘지도않고 해서 테마를 씌우기로한다.

테마를 기웃기웃 거리다보니 예쁜것도 많았지만 기본적으로 아주아주 심플한걸 쓰고싶었고 
디자인적인건 고칠 수 있으니 레이아웃이 맘에드는 테마를 쓰라는 좋은 충고가 쓰인 [글](http://jihyeleee.com/blog/third-designer-can-make-jekyll-blog/) 을 발견하게된다 

고심끝에 [Lanyon](http://lanyon.getpoole.com) 이라는 테마를 고르게 되었고 적용방법은 그냥 통채로 다운받아서 내 jekyll폴더에 덮어쓰면된다. 요목조목 뜯어보면서 이게 뭔지 저게 뭔지 파악중이다..


## jekyll 디렉토리 구조
- _layout
    > default.html, page.html, post.html 기본 레이아웃 파일들

- _posts
    > 연-월-일-제목.md 포스팅 작성

- _site
    > jekyll이 md파일을 html로 변환한 후 실제 서빙되는 파일들

- public    
    > css같은 정적인 파일들이 들어있는듯 하다..

- _config.yml
    > 여러 환경변수들이 설정되어있다. 아무데서나 참조 가능


## TODO 앞으로 해야 할 것들
기본적인 세팅이 대강 됐다고 생각하는 지금 시점에서 첫 포스팅을 작성하고 있다.
하지만 아직 기본적으로 있어야할 기능들이 없는것들이 많다.

- ~~댓글 (Disqus)~~ 적용
- 게시물 카테고리(개발 이외에 자동차,오토바이 관련글도 포스팅할 예정)
- 태그 기능
- ~~Google Analytics(방문자 추적, 통계)~~ 적용
- SEO(검색엔진 최적화)
- 테마 다듬기 (사이드바 커스터마이징, 폰트 등등)

긴 글 읽어주셔서 감사드린다는 인사를 드리며 첫 글을 마치겠다.



