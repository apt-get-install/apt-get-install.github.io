---
title: "[Python] 파이썬 통합 개발 환경 설치"
layout: single
date: 2020-06-25 22:00:00 +0900
author: 최수호
toc: true  
toc_sticky: true 
published : true
categories: 
  - python
tags:
  - python
  - Setup
  - Setting
---
# 1. 통합 개발 환경(IDE)
## 01) 통합 개발 환경 이란?
통합 개발 환경(Intergrated Development Environment)은, 프로그래밍을 쉽고 편리하도록 도와주는 여러가지 기능이 추가된 텍스트 에디터라고 생각하면 된다.


## 02) 다양한 통합 개발 환경(IDE)
대표적인 파이썬 통합 개발 환경은 다음과 같다.

* **PyCharm** : Jetbrain사에서 무료버전(Community)을 제공하며, 현재로선 가장 강력한 파이썬 IDE이다. 상업적 목적의 유료버전(Professional)도 판매한다.
* **Visual Studio Code** : 마이크로 소프트사에서 무료로 제공하며, 플러그인(추가 기능)추가로 파이썬 뿐만 아니라 다른 프로그래밍 언어도 사용 가능하다.
* **Eclipse** : 이클립스 재단에서 무료로 제공하며, 플러그인(추가 기능)추가로 파이썬 뿐만 아니라 다른 프로그래밍 언어도 사용 가능하다.

본 포스팅은 이 중 PyCharm을 기준으로 진행하려고 한다.


# 2. PyCharm 설치
## 01) 다운로드
* 사이트 접속 Link: [https://www.jetbrains.com/ko-kr/][jetbrains-site-link]{: target="_blank"}

[jetbrains-site-link]: https://www.jetbrains.com/ko-kr/ "Go jetbrains official site"
![파이참 다운로드](/assets/images/posts/pycharm-download-01.jpg)
PyCharm 항목을 클릭한다.

![파이참 다운로드](/assets/images/posts/pycharm-download-02.jpg)
사이트의 중단이나 우측 상단의 다운로드 버튼 중 아무거나 클릭한다.

![파이참 다운로드](/assets/images/posts/pycharm-download-03.jpg)
Community 버전을 다운로드 한다.


## 02) 설치
아래 사진의 순서대로 진행한다. 3번째 사진에서 체크박스 부분은 꼭 체크하고 설치를 진행한다.
![파이참 설치](/assets/images/posts/pycharm-setup-01.jpg)

>[64-bit launcher] : 파이참을 64비트로 실행할 아이콘이 생성된다.

>[Add launchers dir to the PATH] : 환경변수를 설정한다.

>[Add Open Folder as Project] : 폴더 우클릭시, 파이참 프로젝트로 바로 연결할 수 있는 기능이 추가된다. 

>[.py] :  파이썬 파일(.py확장자)을 파이참으로 연결 시켜준다.


## 03) 설치 확인
설치가 완료 되면 다음과 같은 화면이 보일 것이다.
![파이참 설치 완료](/assets/images/posts/pycharm-setup-02.jpg)

[Run PyCharm Community Edition] 체크박스를 체크한 후 Finish버튼을 클릭한다. 그리고 아래 그림에 따라 순서대로 진행한다.

![파이참 실행](/assets/images/posts/pycharm-excute-01.jpg)
>라이센스 동의와 에러 및 기타 정보에 대한 송신 여부에 대한 내용이다.

아래와 같이 [Skip Remaining and Set Defaults]을 클릭한다.
![파이참 실행](/assets/images/posts/pycharm-excute-03.jpg)

다음과 같은 화면이 보이면 정상적으로 설치된 것이다.
![파이참 실행](/assets/images/posts/pycharm-excute-04.jpg)

<script src="https://utteranc.es/client.js"
    repo="apt-get-install/apt-get-install.github.io"
    issue-term="title"
    theme="github-light"
    crossorigin="anonymous"
    async>
</script>