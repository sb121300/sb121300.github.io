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

1) 관리할 계정 id를 등록한다.
<br><img width="1384" alt="2 new_accout" src="https://user-images.githubusercontent.com/96071948/146358820-f5bdf69d-9236-4744-ac36-b3da0835fc61.png"><br>
2) 관리할 블로그 주소와 국가를 변경한다.
<br><img width="1399" alt="3 blog주소등록" src="https://user-images.githubusercontent.com/96071948/146358831-a988a925-d8a4-452b-8f16-03feb1a876da.png"><br>
### ③ 데이터 스트림 생성하기

- path: **관리** > **속성** > **데이터 스트림**

#### [데이터 스트림 추가]

1) github.io의 경우 웹이기 때문에 웹을 선택한다.
<br><img width="1413" alt="4 blog 데이터 등록" src="https://user-images.githubusercontent.com/96071948/146359040-ee87fee0-146f-44ae-bbbe-d018f3a542c0.png"><br>
2) 웹 스트림 설정: **url**과 **스트림 id**를 설정한다.
<br><img width="1160" alt="5-2" src="https://user-images.githubusercontent.com/96071948/146359059-60e36969-f653-4c2c-8ebe-8102c9d299b8.png"><br>
→ 만들어진 데이터 스트림
<br><img width="1432" alt="5  만들어진 데이터스트림" src="https://user-images.githubusercontent.com/96071948/146359061-9e9bd824-8f95-423d-be17-80384469ae1c.png"><br>
## 2. _config.yml 수정

① 웹 스트림의 세부정보에서 **측정 id**를 복사한다.
<br><img width="1351" alt="6  config " src="https://user-images.githubusercontent.com/96071948/146359072-05d614d2-f76d-4274-b57d-510b36cd166c.png"><br>
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
<br><img width="754" alt="7  config yml 수정" src="https://user-images.githubusercontent.com/96071948/146359077-b9042a70-481c-46e1-a469-623769cac5d5.png"><br>

## 3. 실행 화면
<b>분석화면은 다음과 같다</b>
<br><br>
