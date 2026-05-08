User: Pasword 9669

- [anyname].vhdx 만 있으면 VM을 만들 수 있다. HDD가 있는 거니까 그렇다.
- 빨리 만들기 -\> 로컬 설치 원본 -\> 설치 소스 변경에서 위의 vhdx 파일 선택
- ==옵션에서== ==이름== ==변경== - 안 하면 '새 가상 컴퓨터'라는 이름으로 VM이 생긴다.

**오디오** **사용하지** **않기**  
고급세션 설정 단계에서 로컬리소스 \> 설정 \> 원격오디오 사용하지 않음 옵션 선택하면 된다

![F M C H T M.. 0 N](Exported%20image%2020260428061428-0.png)  

고급 세션 변경을 위해 고급세션 설정 팝업을 띄울 필요가 있을 때는 아래와 같이 하라.

7. 탐색기를 열어서 %appdata%\Microsoft\Windows\Hyper-V\Client\1.0 로 이동
8. 아래 샘플처럼 vmconnect.rdp.a5e08a6c-aede-7201a317105c.config 와 같은 모양으로 설정 파일이 있다.
9. 파일을 열어서 직접 편집하거나 삭제한다. 삭제하면 재시작 시 창이 다시 나온다. 
- 가상 컴퓨터 가져오기 \> 가상 시스템 선택에서 C:\Hyper-V\Virtual Machines 선택 \> (복원)기존 고유ID 사용 선택
- 뭔가 추가 선택에서 폴더 선택 시, (기본 폴더 삭제하고)
    - C:\Hyper-V 그리고 기존에 있는 vHDD 폴더 등 선택하면 되네
 
메모리가 모자라다고 하고 부팅 안 될 때  
메뉴바 상의 되돌리기 아이콘을 눌러서 이전 검사점으로 이동하면 된다

![MARKNLJCQI Win 10 Pro VM F meA M 0 V](Exported%20image%2020260428061429-1.png)

Hyper-V 설치  
설정방법 안내 블로그  
[https://itons.net/%EC%9C%88%EB%8F%84%EC%9A%B010-%EA%B0%80%EC%83%81%EB%A8%B8%EC%8B%A0-hyper-v-%EA%B8%B0%EB%8A%A5-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0/](https://itons.net/%EC%9C%88%EB%8F%84%EC%9A%B010-%EA%B0%80%EC%83%81%EB%A8%B8%EC%8B%A0-hyper-v-%EA%B8%B0%EB%8A%A5-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0/)  
윈도우설치 방법  
[https://itons.net/%ea%b0%80%ec%83%81%eb%a8%b8%ec%8b%a0-hyper-v-%ec%9c%88%eb%8f%84%ec%9a%b010-%ec%84%a4%ec%b9%98%ed%95%98%ea%b8%b0/](https://itons.net/%ea%b0%80%ec%83%81%eb%a8%b8%ec%8b%a0-hyper-v-%ec%9c%88%eb%8f%84%ec%9a%b010-%ec%84%a4%ec%b9%98%ed%95%98%ea%b8%b0/)
 
**Windows 10 Pro Key** **쿠팡에서** **구입해서** **설치** **완료**  
현재 발견 문제점  
Guest PC (VM)에 Windows 10 Pro가 설치되어야 Enhanced Session 이 열리고 로컬 기기 연결 메뉴가 나온다  
Enhanced Session 적용하면 로그인 화면이 안 뜨는 문제 해결방법  
[https://www.itexperience.net/blurred-logon-screen-in-hyperv-enhanced-session/](https://www.itexperience.net/blurred-logon-screen-in-hyperv-enhanced-session/)
 ![Use Local Devices and Resources on HyperV Virtual ...](Exported%20image%2020260428061431-2.png)  

[2023-04-08]  
VM Name: Mark-VM  
vHDD File Name: Mark-VM.vhdx  
Virtual HDD at D:\Hyper-V\Hulk-VM\vHDD\  
Virtual Machine (Default Folder) at D:\Hyper-V\Hulk-VM
   

## It's outdated information below ##  
Folder Configuration: [https://www.tenforums.com/tutorials/56837-change-hyper-v-virtual-machines-default-folder-windows-10-a.html](https://www.tenforums.com/tutorials/56837-change-hyper-v-virtual-machines-default-folder-windows-10-a.html)
 
Current status (VM name: Windows 10 Pro VM)  
D:\Hyper-V  
D:\Hyper-V\VM1  
D:\Hyper-V\VM1\Virtual Machines (HDD files) ← 반대 아니냐?  
D:\Hyper-V\VM1\Virtual Hard Disks (VM files)
 
Result: At least, the folder structure is as what I expected.

![Machine generated alternative text Import Virtual ...](Exported%20image%2020260428061433-3.png)

**가상** **컴퓨터** **연결**
   

다른 PC로 Hyper-V VM 옮기기: export and import? [참고링크](https://www.soft2000.com/18296)
    
Localhost PC의 기기 연결 방법 [https://www.tenforums.com/tutorials/58091-use-local-devices-resources-hyper-v-virtual-machine-windows.html](https://www.tenforums.com/tutorials/58091-use-local-devices-resources-hyper-v-virtual-machine-windows.html)  
Host PC에서 PowerShell 관리자 모드 실행  
vmconnect localhost "Win 10 Pro VM" /edit 실행  
아래 창이 올라오면 local resource 등 선택, More 선택하면 host 기기 디바이스 선택 가능