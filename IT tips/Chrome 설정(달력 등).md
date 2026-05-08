**각** **프로파일** **별** **크롬** **실행** **방법**  
"C:\Program Files\Google\Chrome\Application\chrome.exe" --profile-directory="Profile 3"
 
URL도 추가할 수 있다.  
chrome.exe --profile-directory="Default" [www.naver.com](http://www.naver.com)  
chrome.exe --profile-directory="Profile 1" [www.naver.com](http://www.naver.com)  
현재 LG그램 Profile 1: 회사, 2: Mark개인 3: MoneyHul가(n2yskim)
 
맥에서는 아래와 같이 만들어야 한다.  
do shell script "/Applications/Google\\ Chrome.app/Contents/MacOS/Google\\ Chrome --profile-directory='Default' &"
 
**Outlook Calendar Web** **바로가기** **만들기**  
바로가기를 우선 시작 메뉴에 추가한 다음 시작 메뉴에서 그 바로가기를 작업표시줄에 추가한다.  
제대로 동작하지 않을 경우, 작업표시줄에 있는 아이콘의 속성에서 대상에 아래 URL을 입력한다.  
"C:\Program Files\Google\Chrome\Application\chrome.exe" --profile-directory="Profile 2" --new-window --app=https://outlook.office.com/calendar/view/week
 
--app= 이용하면 Address Bar가 없는 Simple Window로 열린다.
 
작업표시줄 Chrome 아이콘 속성을 위 해당 URL로 변경하면 된다
 
아이콘 이미지 위치도 아래로 변경(It doesn't work on LG Gram while it works on NUC.)  
%USERPROFILE%\OneDrive\사진\cal_large.ico  
**NUC****에** **있는** **바로가기** **링크를** **복사해온** **다음** **그램에서** **이리저리** **했더니** **아이콘이** **달력으로** **보이는데****,** **영** **모르겠다****.**
 
**하드웨어** **가속** **관련** **설정**  
설정: 하드웨어 가속을 켜거나 끌 수 있다  
Chrome://flags 에 재정의 소프트웨어 렌더링 Enabled/Disabled 와 위의 하드웨어 가속 설정을 일치시키는 것이 좋다고 한다  
가속을 끄면 GPU를 사용하지 않으므로 네이버 지도에서 로드뷰 같은 게 느리다