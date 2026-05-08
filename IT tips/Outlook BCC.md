내가 보내는 메일에 특정 메일 주소를 자동으로 BCC하는 방법: Visual Basic 사용
 
[https://www.groovypost.com/howto/microsoft/how-to-automatically-bcc-in-outlook-2010/](https://www.groovypost.com/howto/microsoft/how-to-automatically-bcc-in-outlook-2010/)
 
[이 기능이 필요한 이유]  
아웃룩으로 회사 메일을 사용한다.  
보낸 메일은 아웃룩에만 저장된다. hsscr gmail에 내가 보낸 메일도 저장하고 싶다.
 
[해결책]  
아웃룩에서 메일 보낼 때 마다 자동으로 hsscr gmail을 BCC한다.
 
[Note]  
BCC를 해야만 하는 이유:  
CC를 하면 수신자 메일에 hsscr 메일 주소가 보이고 매번 hsscr이 메일 쓰레드에 포함된다.
 
[버그]  
처음에는 BCC가 잘 되다가 다음날이나 두 번째 아웃룩 실행 후엔 안 된다.  
개발도구 \> 매크로 보안 설정을 3 번째 모든 매크로에 알림 설정으로 바꾸면 된다.