도스 명령 창 열고  
netsh wlan delete profile name="무선네트워크이름"  
netsh wlan delete profile name="ben10_2 2"  
SSID가 Samsung 2 와 같이 2가 붙을 때 그 ==SSID== 삭제하는 법  
Registry 설정에 가서 아래 항목으로 가면 삭제할 수 있다. (이 방법이 가장 확실하네.)  
**HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles**
 
==유선== ==네트워크도== =='====네트워크== ==2'== ==로== ==보이면== ==위== ==레지스트리== ==경로에== ==가서== ==수정하면== ==된다==
 
==혹은== ==네트워크== ==초기화를== ==하면== ==유선== ==네트워크== ==SSID====가== ==초기화== ==된다==