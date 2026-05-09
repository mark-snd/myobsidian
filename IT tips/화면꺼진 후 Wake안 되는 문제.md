마지막으로 YouTube Dell Support가 알려준 문제해결사 \> 전원 관련으로 했더니, 이 문제를 마치 해결했다는 것처럼 결과가 나온다. 지켜보자.  
단순히, 내가 설정한 안함을 10분/30분으로 바꿔놨네. 해결 될 리가 없다.  
시스템 \> 전원  
화면 끄기 10분, 절전 전환 30분 설정인데도 잘 되네  
제어판 \> 전원 옵션

- 하드 디스크 5분 끄기
- 절전
    - 절전 모드 전환 30분
    - 절전 모드 해제 타이머 허용은 사용 안 함
- PCI Express는 링크 상태 전원 관리 해제

이상한 건 위 문제해결사 실행 후에 전원 옵션에서 하이브리드 절전 모드 허용 어쩌고가 없어졌다
 
아래도 뭔가 잘 안 되는 듯  
이 친구 [How to Fix PC Not Waki](https://youtu.be/BHZzFyBrdXk)ng Up From Sleep Mode In Windows 10/8.1/7  
아래와 같이 제어판 \> 전원 옵션에서 설정하면 괜찮다.

![[Exported image 20260428061541-0.png]]  
![[Exported image 20260428061543-1.png]]  

윈도우 절전 관련 어떤 설정을 해도 시간이 지나서 화면이 꺼지면 마우스나 키보드 입력이 들어가도 화면이 깨어나지 않는 문제  
윈도우를 재설치해도 동일 현상이 반복되는 것을 볼 때 보안모듈이나 윈도우 설정 문제는 아닌 것 같다.  
모니터와의 궁합이 문제인 것 같다.  
그 전에는 안 그랬는데 키보드 레오폴드로 바꾼 이후부터 그런 거 아닌가 모르겠다. 이건 아니다. 한성키보드도 마찬가지.
 
시도 할 것들

- 일단 윈도우 절전모드는 다 끄고 모니터만 10분 후 절전 모드 켰음. 얘는 안 먹음
- ==화면== ==끄기====(Screen)====는== ==안== ==함====(====기본====: 10====분====)====으로== ==설정====.== ==절전== ==모드====(Sleep)====는== ==15분으로 설정해본다. ←== 일단 이 방법이 먹히는 것 같다. 다만, 모니터 전원을 켜야 한다.
    - Windows 11 설정에서는 화면 끄기를 안함으로 하면 절전모드도 안함으로 바뀐다. 제어판에 가서 하면 된다.
- 전원 옵션 고급 설정 변경 (2020.11.07 이렇게 해 보는 중 ← 이 방식도 안 먹힘
    - 하드디스크 끄기 설정 1000분으로 변경 원래 20분
    - 절전 \> 하이브리드 절전 모드 허용: 해제로 설정 ← 이 메뉴는 절전(Sleep) 안에 없어졌다.
 
아래 것 원래 체크된 건데 언체크 해보란다 (이것도 소용없음)

![[Exported image 20260428061545-2.png]]  

아래 대화에 있는 방법도 다 안 먹힘  
My computer won't wake up from sleep. I have to do a hard reboot to get it work. My only work around is the "put in never sleep".
 
**Tried** this. [https://answers.microsoft.com/en-us/windows/forum/windows_10-power-winpc/my-computer-wont-wake-up-from-hibernation-in/59046caf-6774-4086-8408-2ff7fa13a134?auth=1](https://answers.microsoft.com/en-us/windows/forum/windows_10-power-winpc/my-computer-wont-wake-up-from-hibernation-in/59046caf-6774-4086-8408-2ff7fa13a134?auth=1)  
I had this problem on my desktop. Screen would remain blank after 'sleeping' and wouldn't respond to mouse or keyboard wake-up even though I'd checked those properties in Device Manager.
 
I did find that my USB Hub was enabled to turn off power so try this 'correction'
 
Go to:
 
Device Manager  
Expand Universal Serial Bus Controllers  
Right click USB Root Hub (xHCI)
 
Click on Properties  
Click on Power Management  
Untick 'Allow the computer to turn off this device to save power'
 
Presumably, neither my mouse nor keyboard could 'wake up' my PC because the Hub had been powered down.