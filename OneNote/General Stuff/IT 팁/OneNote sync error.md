We need the password to sync this notebook. (Error code: 0x803D0005) 끝점과 통신하는 동안 '[https://docs.live.net/skydocsservice.svc'](https://docs.live.net/skydocsservice.svc'에서)에서 오류가 발생했습니다.; 서버에서 HTTP 상태 코드 '401 (0x191)', 텍스트 'Unauthorized'을(를) 반환했습니다.; 요청된 리소스를 사용하려면 사용자 인증이 필요합니다.; 작업 식별자가 올바르지 않습니다.
 
위 에러 메시지로 구글링 하면 다양한 솔루션 게시 글이 나온다.  
[https://appuals.com/onenote-needs-a-password/](https://appuals.com/onenote-needs-a-password/)  
[https://windowsreport.com/onenote-needs-password-to-sync/](https://windowsreport.com/onenote-needs-password-to-sync/)
 
아래 방법 소용 없음  
에러난 상태에 자동 싱크는 진행된다.
 
제어판 \> 사용자 계정 \> 자격 증명 관리 \> ==Windows== ==자격== ==증명== ==(Credential Manager)==  
일반 자격 증명 \> Microsoft 계정 관련 항목 삭제
 
OneNote 실행하고 로그인 다시 한다. (안 된다)
 
==아래== ==안내대로== ==캐쉬== ==지우고== ==OneNote== ==다시== ==시작했더니====,== ==괜찮은== ==것== ==같다==  
The issue might be related to your OneNote client/Local PC settings. You may backup then delete the cache:C:\Users\[username]\AppData\Local\Microsoft\OneNote\16.0
 
원본 글 URL: [https://answers.microsoft.com/en-us/msoffice/forum/all/onenote-always-asks-to-sign-in/5a565792-3416-4e42-824c-0d4bc7c229c1](https://answers.microsoft.com/en-us/msoffice/forum/all/onenote-always-asks-to-sign-in/5a565792-3416-4e42-824c-0d4bc7c229c1)