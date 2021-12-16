
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
# google analytics
> 이 post는 [https://velog.io/@eona1301/Github-Blog-방문자-통계Analytics하기](https://velog.io/@eona1301/Github-Blog-%EB%B0%A9%EB%AC%B8%EC%9E%90-%ED%86%B5%EA%B3%84Analytics%ED%95%98%EA%B8%B0) 를 참고하고 있습니다.
> 

## 1. Google Analytics 등록

### ① Google Analytics 접속 후 로그인

### ② 계정을 설정한다.

1) 관리할 계정 id를 등록한다.

2) 관리할 블로그 주소와 국가를 변경한다.

### ③ 데이터 스트림 생성하기

- path: **관리** > **속성** > **데이터 스트림**

#### [데이터 스트림 추가]

1) github.io의 경우 웹이기 때문에 웹을 선택한다.

2) 웹 스트림 설정: **url**과 **스트림 id**를 설정한다.

## 2. _config.yml 수정

① 웹 스트림의 세부정보에서 **측정 id**를 복사한다.

②_config.yml에 다음과 같은 코드를 추가한다.

```bash
# Analytics
analytics:
  provider               : "google-gtag" 
                          # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id          : "측정 id"
    anonymize_ip         : # true, false (default)
```

#### [실행화면]

## 3. 실행 화면
<b>분석화면은 다음과 같다</b>
