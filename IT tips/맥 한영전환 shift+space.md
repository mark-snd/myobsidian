[관련 설명이 있는 블로그](https://sbinroom.tistory.com/entry/Mac-%EC%97%90%EC%84%9C-%ED%95%9C%EC%98%81-%ED%82%A4-%EB%B3%80%EA%B2%BD%ED%95%98%EA%B8%B0)  
사전 작업

- Xcode를 설치한다(plist edit시 필요)

아래와 같이 설정한다

- `Finder` 에서 우클릭 후 `Go to Folder...`를 선택합니다.
- Pop-up 된 검색 메뉴에서 `~/Library/Preferences/com.apple.symbolichotkeys.plist`를 입력합니다.
- `Finder`창에서 `com.apple.symbolichotkeys.plist`를 엽니다. ( `Xcode`이용 )
- `Cmd + F`를 눌러 검색창을 열어 61을 찾습니다.
- `61, value, parameters, item 2`를 순서대로 열어 값을 바꾸어 줍니다. 저와 같이 `Shift + Space`로 변경하고자 하시면 131072를 입력하시면 됩니다. (기존 값: 786,432)

위 설정 후, reboot 후 적용된다.  
주의 (아래 설정은 하지 않아도 되는 것 같다.)

- 설정 \> Keyboard \> Keyboard Shortcuts \> Input Sources 가 아래와 같이 기본 설정 체크 되어야 한다.

![Launchpad Dock isplay Mission Control Keyboard Inp...](Exported%20image%2020260428061123-0.png)   
위 plist 설정 61 항목의 기본 값은 원래 786432 임(아래 참고)

![O Find com.apple.symbolichotkeys.plist com.apple.s...](Exported%20image%2020260428061124-1.png)