# 20223116 이상백 github 블로그 빌드 과정
***

## 1. JEKYLL 설치
<!--more-->
### 1.1 소개
 본 필자는 블로그 설치 환경이 APPLE MACBOOK 이므로 기본적으로 Ruby가 설치 되어있어 여기서 Ruby 설치 과정은 생략한다.
우선 Jekyll 공식 홈페이지에 들어가 Jeykll을 설치한다.

Jekyll 공식 사이트: [Jekyll][JekyllLink]

[JekyllLink]: https://jekyllrb-ko.github.io

### 1.2 jekyll 설치
 본 필자는 mac os 이므로 __iterm2__ 라는 프로그램을 사용하여 설치하였다.   
 터미널에 아래 코드를 입려하면 jekyll이 설치된다.
 <!--more-->
 
 ```bash
gem install bundler jekyll
```

### 1.3 Github에서 레포지스토리 생성하고 local에 clone 하기
 먼저 본인 github에 __username.github.io__ 라는 이름으로 reposistory를 생성한다.
 그런 다음 local에 clone 하고 아래 명령어를 실행행한다.
 <!--more-->
 ```bash
 jekyll new "dirName"
 ```
 그런 다음 먼저 local에서 실행하여 본다
 ```bash
 cd "dirName" 
 bundle exec jekyll serve
 ```

성공적으로 작동하면 본인 github에 push 해주자
```bash
git add *
git commit -m "msg"
git push <저장소명> <브랜치명>
```
여기서 간혹 push가 안되는 경우가 있는 데 이 경우 github Oauth tocken을 확인해보자.

### 1.4 theme 적용 
이제 __jekyll__ 에서 기본으로 제공하는 테마가 아닌 개인의 취향에 맞추어 테마를 정해보자
필자는 많이 사용되고 확장성도 좋은 __"Minimal Mistake"__ 테마를 사용하였다.
인터넷에서 원하는 테마의 압축파일을 다운받고 압축파일 압축을 푼 다음 본인 로컬 레포지스토리에 복사하면된다.

### 1.5 본인에 맞게 __BLOG__ 설명 바꾸기
"_config.yml"의 내용을 마음에 맞게 바꾸어보자
```YAML
title: 본인 블로그 이름
email: 본인 이메일
description: >- # this means to ignore newlines until "baseurl:"
  본인에 대한 설명
github_username: 본인 github 닉네임
search: true
```
그 외에도 다양한 옵션이 있으니 주석부분을 읽어보며 본인의 정보에 맞게 수정하자.

### 1.6 Disqus 댓글기능 추가
 우선 Disqus 홈페이지에 들어가 회원가입을 해주자   
 
Disqus주소 : [Disqus][DisqusLink]

[DisqusLink]: https://disqus.com
### 설치방법
1. Disqus에 회원가입하고 __Get Start__ 를 누른다
2. "I want to install Disqus on my site"를 클릭
3. 설정 후 __WEBSITE NAME__ 을 꼭 기억
4. basic 플랜을 선택
5. 플랫폼을 Jekyll 선택

그 이후 추가 적이 "_config.yml" 의 내용수정이 필요하다.

```YAML
comments: true

comments:
  provider: "disqus"
  disqus:
    shortname: "back2gas"
```
위와 같이 수정해준다.

그러면 본인 블로그 post에 댓글 기능이 생겼을 것이다.