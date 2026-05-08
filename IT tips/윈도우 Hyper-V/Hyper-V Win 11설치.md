2022-08-19 업데이트  
**Windows 11 Home****에서** **설치** **방법**: Win 11 Home은 Hyper-V 지원하지 않으므로 아래 방법대로 뭘 돌려서 다운로드 받아야 Hyper-V 관리자라는 게 생긴다.  
[https://blog.naver.com/85honesty/222725216712](https://blog.naver.com/85honesty/222725216712)  
[https://www.xda-developers.com/how-to-install-hyper-v-windows-11-home/](https://www.xda-developers.com/how-to-install-hyper-v-windows-11-home/) (원작자 설명)
 
Home Edition은 Windows 기능 켜기/끄기만으로 안 된다. 이상한 스크립트를 실행해야 한다.
 
Windows 기능 켜기/끄기로 간다  
Hyper-V 관련된 부분 다 체크한다
 
Windows 11 설치를 하려면 보안 설정에 암호화 지원에 신뢰할 수 있는 플랫폼 모듈 사용에 체크해야 한다. 아래 블로그 참고  
[https://blog.dalso.org/article/hyper-v%EC%97%90-windows-11-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0-hyper-v-tpm-%ED%99%9C%EC%84%B1%ED%99%94](https://blog.dalso.org/article/hyper-v%EC%97%90-windows-11-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0-hyper-v-tpm-%ED%99%9C%EC%84%B1%ED%99%94)
 
이유: Win 11에서 키움 HTS 안랩 보안 키보드 경고 자꾸 뜬다  
Windows 11을 Windows 10으로 내리기 - 새로 10을 설치해야 함  
공인인증서 파일 위치:  
C:\Users\user\AppData\LocalLow\NPKI\SignKorea\USER\cn=김동건-17199532,ou=HTS,ou=미래에셋대우,ou=증권,o=SignKorea,c=KR
 
백업: Host PC의 공유폴더에 복사. 나중에 저 위 원래 경로에 복사해야 함(완료)
 
VM 설정에서 부팅 순서를 DVD로 하고 DVD에 iso 연결해서 부팅해보자  
Press Any Key.. 할 때 키보드 아무거나 눌러야 Windows 10 설치 진행한다.
 
재부팅 후 준비 중이라는 말 나올 때 10분 이상 기다리면 다음 단계로 넘어간다  
user 로 로그인한 상태인데, Win 10 Pro 정품인증이 되었다고 하네