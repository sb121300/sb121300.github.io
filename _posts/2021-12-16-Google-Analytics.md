---
layout: post
title: google analytics
excerpt: "추가과제- google analytics를 이용한 방문자 분석"
author: soobin Kim
categories:
  - 추가과제
tags:
- google analytics
- Jekyll
date: 2021-12-16
---

> 이 post는 [https://velog.io/@eona1301/Github-Blog-방문자-통계Analytics하기](https://velog.io/@eona1301/Github-Blog-%EB%B0%A9%EB%AC%B8%EC%9E%90-%ED%86%B5%EA%B3%84Analytics%ED%95%98%EA%B8%B0) 를 참고하고 있습니다.
> 

## 1. Google Analytics 등록

### ① Google Analytics 접속 후 로그인
<br><img width="1414" alt="1 login" src="https://user-images.githubusercontent.com/96071948/146358801-1f392c09-d220-497e-b00e-6a5a1bbe23d4.png"><br>
### ② 계정을 설정한다.

-1) 관리할 계정 id를 등록한다.
<br><img width="1384" alt="2 new_accout" src="https://user-images.githubusercontent.com/96071948/146358820-f5bdf69d-9236-4744-ac36-b3da0835fc61.png"><br>
-2) 관리할 블로그 주소와 국가를 변경한다.
<br><img width="1399" alt="3 blog주소등록" src="https://user-images.githubusercontent.com/96071948/146358831-a988a925-d8a4-452b-8f16-03feb1a876da.png"><br>
<b>-3) 고급 옵션을 설정한다.</b>
<br><img width="1393" alt="3-2  고급옵션 설정" src="https://user-images.githubusercontent.com/96071948/146374514-fc7e4d43-08f3-404e-a6cd-9a5e9766d351.png"><br>

## 2. 추적 코드 확인 및 코드 수정
- path: **관리** > **속성** > **추적 정보** > **추적 코드**

### ① _config.yml 수정

-1) 추적 id를 복사한다.
<br>
<img width="1434" alt="추적id" src="https://user-images.githubusercontent.com/96071948/146375002-09cd45d8-5dfe-42bc-af6f-9459e7132f13.png">
<br>

-2) 추적 id를 포함한 다음 코드를 **_config.yml** 에 추가한다.
```bash
# Analytics
analytics:
  provider               : "google" 
                          # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id          : "{추적 id}"
    anonymize_ip         : # true, false (default)
```

[수행 화면]
<br><img width="709" alt="추적 Id-visualcode" src="https://user-images.githubusercontent.com/96071948/146375568-425a770f-625c-4907-9ccb-6d88aa7eb31f.png"><br>

### ② google-analytics.html 파일 수정
- _includes 폴더의 google-analytics.html을 수정한다.
- 웹사이트 추적의 범용 사이트 태그(gtag.js)를 복사한다.

<br><img width="1018" alt="범용태그" src="https://user-images.githubusercontent.com/96071948/146376415-e767bd35-a38a-463d-adbd-afa0ce369016.png"><br>


```html
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-215554982-2"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-215554982-2');
</script>
```



### ③ html 상단에 include 하기
포스트의 html <head> 태그 내에 
```html
{% include google-analytics.html %}
```
을 추가한다.<br>
  
  
<br><img width="1182" alt="head tag" src="https://user-images.githubusercontent.com/96071948/146365822-d3d6e3cf-9e11-4c8a-ab71-7594c7870670.png"><br>
## 4. 실행 화면
<b>분석화면은 다음과 같다</b>
<br><img width="466" alt="추적하기" src="https://user-images.githubusercontent.com/96071948/146376436-e3ccaa68-b7a7-4874-990b-594d1f648481.png"><br>
* 1명의 활성화된 사용자 즉, 작성자인 본인이 계속 check하면서 조회 중이므로 다음과 같이 뜬다.
[트래픽 보고서]
<br><img width="1440" alt="추적상세" src="https://user-images.githubusercontent.com/96071948/146376641-a3e66e9a-7b3c-41c5-a4d3-6feaf4d11ed6.png"><br>

### google analytics가 잘 수행되고 있는 지 실험해보기.
- 네이버 웨일과 구글로 동시에 다른 메뉴를 접속해보았다.
<br>[실험화면]
<br><img width="1440" alt="추적 실험" src="https://user-images.githubusercontent.com/96071948/146378893-5e4d02dc-d3e2-4f20-b702-5db9401cdbc0.png"><br>
<br>[트래픽 보고서]
<br><img width="1440" alt="추적 실험2" src="https://user-images.githubusercontent.com/96071948/146378933-c26878a5-38ea-46dd-8016-131207c74af2.png"><br>
<br>▶ 결과적으로 2명이 메뉴에 잘 접속한 것이 조회되며 google analytics 연동이 잘 된 것으로 확인된다.
