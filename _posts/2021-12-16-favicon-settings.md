---
layout: post
title: Favicon 추가하기
excerpt: "사이트에 favicon 추가"
author: soobin Kim
categories:
  - 추가과제
tags:
- favicon
- Jekyll
date: 2021-12-16
---


> 이 포스트는 [https://min9nim.github.io/2018/03/add-favicon/](https://min9nim.github.io/2018/03/add-favicon/) 과
> 

> [https://velog.io/@eona1301/Github-Blog-파비콘Favicon-세팅하기](https://velog.io/@eona1301/Github-Blog-%ED%8C%8C%EB%B9%84%EC%BD%98Favicon-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0) 를 참고하고 있습니다.
> 

- 사용한 image는 다음과 같습니다.
<br>![developer](https://user-images.githubusercontent.com/96071948/146361868-c01639fa-b38a-4698-9fcd-c80317c05367.png)<br>

## 1. [https://realfavicongenerator.net/](https://realfavicongenerator.net/) 에서 favicon 생성

### [생성된 화면]
<br>![favicon](https://user-images.githubusercontent.com/96071948/146361876-d1a606a2-dd1c-48dc-affa-77eab4b06269.png)<br>
→ img 패키지를 저장하고 생성된 코드를 복사합니다.

## 2. 저장된 패키지 업로드

### ① favicon 생성 페이지에서 저장한 패키지를 압축해제 한다.

### ② base 폴더의 assest 폴더의 logo.ico 폴더를 생성한다.

### ③ logo.ico에 해당 img 파일 전부를 붙여 넣는다.

### ④ 결과 페이지의 code를 복사하여 _includes 폴더의 custom-head.html에 붙여 넣기 한다.

custom-head.html의 경로: /sb121300.github.io/_includes/custom-head.html

**★ 주의사항:** 코드를 그대로 붙여넣기 하면 안된다.

→경로의 설정이 중요하다.

-1) **_config.yml** 파일에서 base url을 설정한다.

```html
url : https://sb121300.github.io
```

-2) 다음과 같이 base url에서 시작하도록 경로를 수정한다.

```html
<link rel="apple-touch-icon" sizes="180x180" href="{{site.url}}/assets/logo.ico/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="{{site.url}}/assets/logo.ico/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="{{site.url}}/assets/logo.ico/favicon-16x16.png">
<link rel="manifest" href="{{site.url}}/assets/logo.ico/site.webmanifest">
<link rel="mask-icon" href="{{site.url}}/assets/logo.ico/safari-pinned-tab.svg" color="#5bbad5">
<meta name="msapplication-TileColor" content="#da532c">
<meta name="theme-color" content="#ffffff">
```
#### [설정화면]
<br><img width="542" alt="url" src="https://user-images.githubusercontent.com/96071948/146362041-680ecea8-01d2-4ed9-8ebe-f2a97d592914.png"><br>
## 3. 실행화면
<br><img width="91" alt="favicon2" src="https://user-images.githubusercontent.com/96071948/146362047-a0f867d1-7eee-4076-b0e5-9b7e5a0867b7.png"><br>
- page 이름 옆에 아이콘이 떠있는 것을 볼 수 있다.
