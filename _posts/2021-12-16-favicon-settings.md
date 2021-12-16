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
last_modified_at: 2021-12-16 01:08:25 +0800
---

> 참고 자료
https://velog.io/@eona1301/Github-Blog-파비콘Favicon-세팅하기

https://min9nim.github.io/2018/03/add-favicon/

1. 사용 이미지

2. 과정
① https://realfavicongenerator.net/ 에서 이미지를 이용하여 favicon 생성

② 결과 페이지에 있는 패키지 저장
base 폴더의 assest 폴더의 logo.ico 폴더를 생성한다.
다운받은 패키지를 압축해제하고 logo.ico에 붙여 넣는다.
③ 결과 페이지의 code를 복사하여 _includes 폴더의 custom-head.html에 붙여 넣기 한다.
*주의사항*
- _includes 폴더에서 assets로 이동하는 경로를 정확하게 입력해야한다.
/code
href="apple-touch-icon.png"

href="../assets/logo.ico/apple-touch-icon.png" 로 변경

3. 실행화면 