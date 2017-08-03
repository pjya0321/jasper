---
layout: post
title: Ettercap 을 이용한 누킹
description: "Ettercap 을 이용한 누킹공격"
modified: 2017-08-04
tags:[penetration_testing,DNS_Nuking]
categories:[penetration testing]
image:
    feature:
    credit:
    creditlink:
author:
    name: "박준영"
    bio: 하움... 졸리다
    email: pjya0321@naver.com
    github: jy31241
    site: https://pjya0321.github.io/
---
칼리 내장툴 Ettercap을 사용한 간단한 DOS 누킹 공부.  

먼저 간단한 코드를 하나 짜준다.  

![1]({{ site.url }}/assets/postimage/DN1.png)

Ettercap의 기능인 drop와 kill 함수를 사용 할 때 마다 메시지를 출력하게 했다.  

![2]({{ site.url }}/assets/postimage/DN2.png)

etterfilter dos.elt -o dos.ef 을 입력해서 ef파일을 생성해준다  
etterfilter의 도움말을 보면 -o 는 파일을 아웃푼해준다. 라는 설명이 있다.  

![3]({{ site.url }}/assets/postimage/DN3.png)

ettercap -i eth0 -T -q -F dos.ef -M ARP 명령어를 입력한다.  
각 명령어 도움말은  
i, --iface <iface>         use this network interface  
T, --text                  use text only GUI  
Q, --superquiet            do not display user and password  
F, --filter <file>         load the filter <file> (content filter)  
M, --mitm <METHOD:ARGS>    perform a mitm attack  

![4]({{ site.url }}/assets/postimage/DN4.png)
![4]({{ site.url }}/assets/postimage/DN5.png)

윈7의 브라우저가 뻗었습니다.  
끝  