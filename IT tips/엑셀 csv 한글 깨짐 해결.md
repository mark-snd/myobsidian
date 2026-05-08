UTF-8을 엑셀에서 열면 한글이 깨진다.  
ANSI를 열면 안 깨진다.
 
The best way to handle this issue (Windows 11)

- CSV encoding 확인 (메모장에서 열면 우하단에 보인다)
- ANSI 이면 엑셀에서 한글이 잘 보인다.
- 이 상태로 엑셀에서 작업 완료한다.
- 메모장에서 이 파일을 열면 ANSI이다. 다른 이름 저장을 UTF로 한다.
- Jira upload에서 사용한다.
 
macOS

- Jira export csv를 Google Sheets에서 open 한다(Open with Google Sheets)
- 한글로 편집한다
- File \> Download \> csv 저장
- Jira에 import할 때 UTF-8 선택하고 import하면 된다.