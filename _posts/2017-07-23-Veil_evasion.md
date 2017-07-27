---
layout: post
title: Veil을 이용한 백신우회 악성코드 생성
description: "Veil"
modified: 2017-07-25
tags: [penetration_testing,Metasploit,Veil,Backdoor]
categories: [penetration testing]
image:
    feature:
    credit:
    creditlink:
author:
    name: "박준영"
    bio: 아아 BOB되고싶다
    email: pjya0321@naver.com
    github: jy31241
    site: https://www.instagram.com/jypark_321/
---
먼저 설치한다.  
apt-get install veil-evasion  


/usr/share/veil-evasion 경로에 실행파일 있고  
/var/lib/veil-evasion 경로에는 아웃풋이 저장된다.  

./Veil-Evasion.py 을 실행시킨다.  

![1]({{ site.url }}/assets/postimage/Veil1.png)

실행화면이다.  
1. list를 입력해서 페이로드 목록들 중에서 선택한다.  
2. 셋팅화면에서 로컬호스트 주소를 설정해준다.  
3. generate 로 들어간다.  
4. 악성파일 이름을 정해준다.  
5. 디폴트값 입력해주고 엔터  

![2]({{ site.url }}/assets/postimage/Veil2.png)

그러면 자동으로 핸들러가 생성되고 악성파일도 생성된다.  
경로는 생성창에서 볼 수 있다.  

생성한 파일을 백신이 켜져있는 곳에 놔도 감지가 안된다.  

생성된 핸들러를 메타스플로잇 콘솔로 실행시키고,  
악성파일을 윈10 윈도우디펜스가 켜진 곳에서 실행시켰다.  

![3]({{ site.url }}/assets/postimage/Veil3.png)  

세션 열렸다 잘된다.