---
layout: post
title: Favicon 세팅하기
excerpt: "사이트에 favicon 추가"
author: soobin Kim
categories:
  - 추가과제
tags:
- favicon
- Jekyll
date: 2021-12-16
---
# favicon

---
# favicon

---

> 이 포스트는 [https://min9nim.github.io/2018/03/add-favicon/](https://min9nim.github.io/2018/03/add-favicon/)
> 

> [https://velog.io/@eona1301/Github-Blog-파비콘Favicon-세팅하기](https://velog.io/@eona1301/Github-Blog-%ED%8C%8C%EB%B9%84%EC%BD%98Favicon-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0) 를 인용하고 있습니다.
> 

- 사용한 image는 다음과 같습니다.

## 1. [https://realfavicongenerator.net/](https://realfavicongenerator.net/) 에서 favicon 생성

[생성된 화면]

→ img 패키지를 저장하고 생성된 코드를 복사합니다.

## 2. 저장된 패키지 업로드

### ① favicon 생성 페이지에서 저장한 패키지를 압축해제 한다.

### ② base 폴더의 assest 폴더의 logo.ico 폴더를 생성한다.

### ③ logo.ico에 해당 img 파일 전부를 붙여 넣는다.

### ④ 결과 페이지의 code를 복사하여 _includes 폴더의 custom-head.html에 붙여 넣기 한다.

custom-head.html의 경로: /sb121300.github.io/_includes/custom-head.html

**★ 주의사항:** 코드를 그대로 붙여넣기 하면 안된다.

→경로의 설정이 중요하다.

1) **_config.yml** 파일에서 base url을 설정한다.

```html
url : [https://sb121300.github.io](https://sb121300.github.io/)
```

2) 다음과 같이 base url에서 시작하도록 경로를 수정한다.

```html
<link rel="apple-touch-icon" sizes="180x180" href="{{site.url}}/assets/logo.ico/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="{{site.url}}/assets/logo.ico/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="{{site.url}}/assets/logo.ico/favicon-16x16.png">
<link rel="manifest" href="{{site.url}}/assets/logo.ico/site.webmanifest">
<link rel="mask-icon" href="{{site.url}}/assets/logo.ico/safari-pinned-tab.svg" color="#5bbad5">
<meta name="msapplication-TileColor" content="#da532c">
<meta name="theme-color" content="#ffffff">
```

## 3. 실행화면

