---
layout: post
title: 댓글 기능 추가하기
excerpt: "DISQUS을 이용한 댓글 기능 추가하기"
author: soobin Kim
categories:
  - 추가과제
tags:
- DISQUS
- Jekyll
date: 2021-12-16
last_modified_at: 2021-12-16 01:08:25 +0800
---

> 이 포스트는 [https://velog.io/@eona1301/Github-Blog-%EB%8C%93%EA%B8%80-%EA%B8%B0%EB%8A%A5-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0](https://velog.io/@eona1301/Github-Blog-%EB%8C%93%EA%B8%80-%EA%B8%B0%EB%8A%A5-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0) 를 인용하고 있습니다.
> 

## 1. DISQUS 가입하기

### ① [DISQUS](https://disqus.com/) 에 접속 후 가입한다.

### ② profile 등록과 new site를 등록한다.

1) Profile 등록

2) new site 등록

**Website Name 에 블로그의 url을 기입한다.**

### ③  **_config.yml** 파일 수정

1) admin 사이트 접속

2) shortname 찾기

shortname은 admin 메뉴로 들어갔을 때 url의 첫 부분이다.

3) code 수정

```html
comments:
  provider: "disqus" 
  disqus:
    shortname : "sb121300-github-io"
```

[수행 화면] 

### 2. 댓글을 설정하고자 하는 Html 수정하기

★ post 하단에서만 댓글을 남기도록 설정하였다. (about me 파일에서는 댓글을 남기지 못합니다.)

### ① admin > start > install disqus > **install instructions** 메뉴로 접속하여 <b>첫번째</b> 코드를 복사한다.

### ② 댓글을 허용하고자 하는 html 하단에 html 코드를 넣는다.

```html
<div id="disqus_thread"></div>
<script>
  /**
  *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
  *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
  /*
  var disqus_config = function () {
  this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
  this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
  };
  */
  (function () { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://https-sb121300-github-io.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
  })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by
    Disqus.</a></noscript>
```

## 3. 실행 화면

### [댓글 화면]

### [DisQus에서 댓글 조회]

