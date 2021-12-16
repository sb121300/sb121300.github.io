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

-1) Profile 등록
<br>![1  profile](https://user-images.githubusercontent.com/96071948/146370152-06012b79-3435-4b92-bcc8-1e3ba06e8d60.png)<br>
-2) new site 등록

**Website Name 에 블로그의 url을 기입한다.**
<br><img width="700" alt="2  new_site" src="https://user-images.githubusercontent.com/96071948/146369500-d11b9ad6-6885-4c68-9dd2-19c9d952a345.png"><br>
### ③  **_config.yml** 파일 수정

-1) admin 사이트 접속
<br><br>
-2) shortname 찾기

shortname은 admin 메뉴로 들어갔을 때 url의 첫 부분이다.
<br><img width="855" alt="3 shortname" src="https://user-images.githubusercontent.com/96071948/146369615-5570d20f-870a-4f3c-af7c-da1d68b8291e.png"><br>
-3) code 수정

```html
comments:
  provider: "disqus" 
  disqus:
    shortname : "sb121300-github-io"
```

[수행 화면] 
<br><img width="626" alt="4   config 수정" src="https://user-images.githubusercontent.com/96071948/146369619-16d26395-1ca0-45ec-b6ce-12045da9fb48.png"><br>
### 2. 댓글을 설정하고자 하는 Html 수정하기

★ post 하단에서만 댓글을 남기도록 설정하였다. (about me 파일에서는 댓글을 남기지 못합니다.)

### ① admin > start > install disqus > **install instructions** 메뉴로 접속하여 <b>첫번째</b> 코드를 복사한다.
<br><img width="1420" alt="5  url2" src="https://user-images.githubusercontent.com/96071948/146369634-342c048e-2e4a-4a70-a9f9-8b87d82b855d.png"><br>
### ② 댓글을 허용하고자 하는 html 하단에 html 코드를 넣는다.
<br><img width="1176" alt="5  url3" src="https://user-images.githubusercontent.com/96071948/146369639-35c12350-5594-4146-b849-5cf6b1bd60a2.png"><br>
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
<br><img width="1078" alt="7  댓글예시2" src="https://user-images.githubusercontent.com/96071948/146369642-c2aace45-7834-4ab4-be25-ca5eedc6f36b.png"><br>
### [DisQus에서 댓글 조회]
<br>
<img width="1326" alt="8 댓글예시" src="https://user-images.githubusercontent.com/96071948/146369647-16d822c1-1234-4780-8951-6952dbd8668c.png"><br>
<b>DISQUS</b>의 <b>admin</b>으로 접속하면 그동안 기록되었던 comment를 볼 수 있다.
