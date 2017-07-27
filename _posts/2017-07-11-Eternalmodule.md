---
layout: post
title: Eteranalblue + Douublepusal 모듈
description: "ShadowBroker"
modified: 2017-07-11
tags: [penetration_testing,shadow broker,Metasploit]
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
이전에 포스팅한 이터널블루와 더블푸자의 익스플로잇 모듈이 있다고 한당.  
일단 smb취약점을 이용한 실습이기때문에 모듈을 사용해서 smb취약점을 확인하려고 모듈을 키려는데, 업뎃을 하도안해서 그런지 없어서 모듈을 다운받았다.  

https://github.com/jy31241/metasploit-framework/blob/master/modules/auxiliary/scanner/smb/smb_ms17_010.rb  

![1](assets/postimage/EtMo1.png)

모듈 실행시키고 타겟의 아이피 주소를 rhosts에 설정하고 익스플로잇한다.  
그러면 호스트 이스 취약점 있다! 라고 나옵니다.  

![2](assets/postimage/EtMo2.png)

그리고 다운받은 이터널블루 더블푸자 모듈을 smb모듈 폴더에 집어넣고 리로드한다.  

![3](assets/postimage/EtMo3.png)

모듈을 실행시키고 셋팅을 쭉 해준다  
타겟이 64비트면 lsass.exe로 해주고 32비트는 exeplorer.exe로 해준다  

![4](assets/postimage/EtMo4.png)

타겟 운영체제에 맞춰서 설정한다.  

![5](assets/postimage/EtMo5.png)

그리고 페이로드도 설정해준다.  
로컬호스트는 칼리주소로 설정한다. 설정을 끝내면 위와같은 모습이다.  

![6](assets/postimage/EtMo6.png)

익스플로잇을 해봤다. 잘된다  

![7](assets/postimage/EtMo7.png)

아주잘된다.  
커버로스짱



