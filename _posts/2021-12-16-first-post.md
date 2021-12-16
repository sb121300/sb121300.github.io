---
layout: post
title: github.io build 과정
excerpt: github.io build
author: soobin Kim
categories:
  - 필수과제
tags:
- Github
- Jekyll
date: 2021-12-16
---

[link to my [github.io](http://github.io/)] ([https://sb121300.github.io](https://sb121300.github.io/))

- 사용 os: Mac-os
- Visual Studio code3 & iTerm

## 1. [github.io](http://github.io) 생성

① [github.io](http://github.io/) 레포지터리 생성

② 원격저장소와 로컬 저장소 연결하기

 로컬에서 원격저장소를 clone할 로컬 저장소를 생성한 후, 생성된 로컬 저장소에 git clone 합니다.

```bash
mkdir <저장소 이름>
cd <저장소 이름> #연결할 로컬 저장소 생성 후, 이동

git init
git clone "git저장소 url" #원격 저장소와 로컬 저장소 연결
```

## 2. Jekyll 환경 설정

① ruby 가장 최근의 version으로 버전 변경

Mac os의 경우에는 ruby가 이미 설치되어 있기 때문에 업데이트 과정을 거치면 된다.

ruby의 버전을 변경하기 위해 rbenv를 사용한다.

```bash
brew update #brew를 이용해 rbenv를 설치하기 때문에 사전에 update한다.
brew install rbenv ruby-build #rbenv install
rbenv install -l #ruby 버전들 확인
rbenv install 3.0.3 #가장 최근 버전인 3.0.3을 설치한다.
rbenv global 3.0.3
```

* 발생하는 에러:

ERROR:  While executing gem ... (Gem::FilePermissionError)

→ 환경 변수 설정을 통해 해결해준다.

```bash
echo '# rbenv' >> ~/.bash_profile 
echo 'export PATH=~/.rbenv/bin:$PATH' >> ~/.bash_profile 
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile 
#bash container를 사용하기 때문에 bash_profile에 저장한다.
source ~/.bash_profile
```

- [https://happymemoryies.tistory.com/21](https://happymemoryies.tistory.com/21)

② jekyll bundler 설치

```bash
gem install jekyll bundler
```

## 3. Jekyll 테마 정하기

강사님께서 제공한 [http://jekyllthemes.org/](http://jekyllthemes.org/) 사이트에서 blog posting에 적절한 테마를 찾습니다.

[http://jekyllthemes.org/themes/not-pure-poole/](http://jekyllthemes.org/themes/not-pure-poole/) 

**not pure poole** 테마 선정

② zip file 다운 후, 압축해제

③ sb121300.github.io에 압축해제한 file들을 모두 복사 붙여넣기 합니다. 

## 4. Blog 기본 설정

Blog 의 기본 설정을 담당하는 로그 파일은 **_config.yml** 입니다.

해당 파일에서 주소와 img 기본 설정, post 기본 설정을 만들고자 하는 블로그 주소에 맞게 수정하였습니다.

## 5. serve code

bundle 라이브러리를 이용해 Blog의 변경사항을 실시간으로 볼 수 있다.

[code]

```bash
bundle exec jekyll serve

또는 
bundle exec jekyll serve --trace
```

- 발생 에러
    - `require': cannot load such file -- webrick (LoadError)
    
    ```bash
    bundle add webrick
    ```
    

## 6. 원격 저장소에 push & 블로그 호스팅하기

 원격 저장소에 push 한다.

처음 push를 하는 경우 personal token을 이용해 로그인 한 뒤 push 할 수 있다

### [실행 화면]
![git-main](https://user-images.githubusercontent.com/96071948/146340054-96f0512a-8da9-44eb-8610-618b696a6d15.png)
