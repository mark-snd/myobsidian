Blog: [https://kibua20.tistory.com/138](https://kibua20.tistory.com/138)
 
Scrcpy  
S10 IP Address 192.168.0.85
 
WiFi connect (WiFi라도 폰 USB 디버깅 모드는 On해야 함)  
To connect to your phone  
adb connect 192.168.0.85:5555
 
1. 스마트폰을 컴퓨터에 USB로 연결하고, 터미널에서 아래 명령어를 입력해주세요.  
$ adb tcpip 5555  
(성공 시) : restarting in TCP mode port: 5555  
* 매번 USB연결이 귀찮다면 setprop  
$ adb shell setprop service.adb.tcp.port 5555
 
2. 스마트 폰의 USB 연결을 해제하고 터미널에서 아래 명령어로 무선 연결  
$adb connect \<Smart Phone IP\>:5555
 
To disconnect  
adb -s 192.168.0.85:5555 disconnect  
adb disconnect (Disconnect all devices attached)
 
Sndcpy (Sound를 PC로 보내는 것)  
[https://kibua20.tistory.com/182](https://kibua20.tistory.com/182)  
개발자 글 [https://blog.rom1v.com/2020/06/audio-forwarding-on-android-10/](https://blog.rom1v.com/2020/06/audio-forwarding-on-android-10/)  
Phone에서 해당 apk가 돌고 있으면 PC에서 sndcpy 실행하지 않아도 소리는 PC에서 나온다
 
Script로 sndcpy 기능을 죽이는 방법을 찾아야 한다  
adb -s 192.168.0.85:5555 shell am force-stop com.rom1v.sndcpy