---
title: "나의 블로그에 Google Analytics 적용하기"
excerpt_separator: "<!--more-->"
categories:
  - 유레카프로젝트
tags:
  - 과제
  - blog
---

## __1. Google Analytics 적용을 위한 Google Analytics 설정__
[GoogleAnalyticsLink]: https://analytics.google.com/analytics/web/provision/#/provision

<!--more-->

 * 우선 [__GoogleAnalytics__][GoogleAnalyticsLink]에 접속한다.
 * 만약 __Google__ 아이디가 없다면 먼저 __Google__ 아이디를 만들어야 한다.

 여기서 본 필자는 __Minimal Mistake__ 라는 Jekyll 테마를 사용하였는데 여기서는 기본적으로 __Google Analytics__ 에 대한 파일이 들어 있고 **_config.yml** 파일에 약간만 수정을 하면된다.

 하지만 그 전에 몇가지 수행해야할 과정이 있다.

<img src="https://github.com/back2gas/back2gas.github.io/blob/master/assets/images/GASC1.png?raw=true" width="450px" height="300px" title="px(픽셀) 크기 설정" alt="Screenshot1"><br/>

웹스트림에 본인의 블로그를 등록한다.
그러면 웹 스트림 세부정보 분석에서 다음과 같은 정보들을 볼 수 있을텐데 그 중 __측정ID__ 를 복사해주자.

## **2. _config.yml 수정**
**_config.yml**에 다음 내용을 추가해 주자.
``` yaml
analytics:
  provider               : "google-gtag" 
                          # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id          : "본인 추적 ID"
    anonymize_ip         : # true, false (default)
```

그리고 수정된 내용을 github에 push하자.

```bash
git add *
git commit -m "msg"
git push <저장소명> <브랜치명>
```

그러면 일정시간 이후 본인의 blog가 연동된 것을 확인 할 수 있을 것이다.

## __3. 연동이 잘 되었는지 확인__

<img src="https://github.com/back2gas/back2gas.github.io/blob/master/assets/images/GASC2.png?raw=true" width="450px" height="300px" title="px(픽셀) 크기 설정" alt="Screenshot1"><br/>

잘 연동이 된것을 확인할 수 있다.
