문제 발생

- 현재 w ('ㅈ')이 잘 안눌려지는 현상이 있다.
- 주로 외국 웹 사이트에서 그런 것 같다. Geminia, ChatGPT 등
- 키캡 아래 꽂는 그 녀석(스위치)을 교체해야 하나? 뭐라고 부르더라?
- 우선, 스위치를 다른 것과 교체해보자.

전용 소프트웨어(F.L. Driver) 계정

- gmail로는 회원 등록 안됨
- brainkim@네이버, cmk75도토리1 으로 성공함
  
내가 중고로 사온 녀석은 오테뮤 **저소음** **피치**(실리콘 흡음재 포함)  
오테뮤 저소음 라임/크림 스위치도 있다.
 
- 결론: 약 두 달 사용 가능한 거네.
 
Fn + '\' 은 LCD 창 on/off  
Fn + Ins = LCD 를 시계와 이미지 toggle 선택  
Fn + Del = 키보드 백라이트 on/off
 
블루투스 연결  
- 스위치를 BT로 바꾼다.  
- FN + 1을 3초간 누르면 1번 대기 상태 진입함
 
전용 소프트웨어  
LCD screen 이미지 관련 작업은 Screen 메뉴에서 한다.
 
우측 4개 키 기존 순서(위부터): Ins Del PgUp PgDn이다. PgDn -\> End 로 설정하기  
Windows 설정

- AutoHotKey를 이용했다.
    - Karabiner에서 아래와 같이 설정한다.
    - Simple Modifications로 가서 CMK75는 ROYUAN이라는 걸로 인식
    - 아래 그림과 같이 설정했다. (4/2/25 6:42 AM 기준, 이게 안 먹힘)
- ![[Exported image 20260428061111-0.png]]
    - Home, End 는 Arrows Key 카테고리에 있다.
    - 원래 PgUp은 CMD + 상향 화살표, PgDn은 CMD + 하향 화살표로 사용하면 된다. 
**4/2/25 6:44 AM** **기준****,** **적용한** **방법** **-** Karabiner \> Complex Modifications 에서 Add your own rule에 2개의 rules를 추가했다.

- 주의할 점: Rule 편집기 내에서 코드 편집해야 한다. 다른 텍스트 에디터에서 작업하고 붙여넣기 하면 글자 에러가 난다. 
2.4G 연결 시, 뒷면 아래 LED를 끄면 키보드 LED와 작은 LCD 모두 꺼진다.  
시계를 LCD 창으로 보려면 뒷면 스위치를 끄면 안 된다.
 
전용 소프트웨어 LED설정에서 LED 모드르 Shadowing으로 선택하면 그나마 타이핑 먹은 키에만 불이 들어온다. 배터리 전력 소모를 줄이기엔 이 방법 밖에 없다.  
OS 영어 모드 시, Light \> Light Mode: Shadowing 선택
 
**OLED** **시간** **동기화**  
- OLED 설정 \> (오른쪽 패널) 기타 설정 \> 화면시간 동기화  
OS가 영어 모드일 때는 아래 메뉴 확인  
Screen \> (오른쪽) Other Settings \> Sync time on screen
 
전용 소프트웨어 문제점  
키 매핑을 할 때, 한 개의 키를 조합 키로 변경만 가능하다. 사실 그 반대 니즈가 더 많다!
 
키 조합 설명서  
[https://funkeys.co.kr/bbs/board.php?bo_table=download&wr_id=217](https://funkeys.co.kr/bbs/board.php?bo_table=download&wr_id=217)  
FN + Esc 3초 - 공장 초기화  
FN + 1 등 숫자키3초 누르면 BT 1 번 연결 (같은 방법으로 2, 3, 4 연결)
 
Esc 키캡만 민트로 바꾸면 완전히 Air75  
알리 여기서 '현대둘치'라는 걸 전체 구입해야 함 [링크](https://ko.aliexpress.com/item/1005005945279489.html?spm=a2g0o.productlist.main.7.60ea125bblb86e&algo_pvid=9deb8fef-3d66-41f6-86c9-dd529ad60e2b&algo_exp_id=9deb8fef-3d66-41f6-86c9-dd529ad60e2b-3&pdp_npi=4%40dis%21KRW%2130175%2124143.0%21%21%2122.81%21%21%402103205117039767570662275e1a1b%2112000034968036125%21sea%21KR%212472906319%21&curPageLogUid=pZyKbMW5iFcL) 24,000원 정도
 
**키가** **씹히는** **문제** **2024-10-21****에** **시도한** **방법**  
증상: 영어 L키 즉 모음 'ㅣ'가 안 눌러지는 현상 발생  
해결: 키캡을 뽑고, 스위치를 옆에 있는 K와 교체하여 꽂아 보았다. 일단, 잘 되는 것 같다.
 
배터리
      

**macOS** **설정**