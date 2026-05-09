# Vault Log

append-only. grep 가능한 형식으로 유지.

---

## [2026-04-26] create | 이전 위키 시스템 초기화 (index.md, log.md, SCHEMA.md 생성)
- Domain: 개인 지식 관리(PKM) + 회사 업무 기억
- 구조: raw/, entities/, concepts/, comparisons/, queries/
- 참고: 해당 시스템은 2026-05-08 CLAUDE.md 방식으로 통합됨. SCHEMA.md는 raw/에 아카이브됨.

## [2026-05-08] lint | CLAUDE.md 구조 전면 개편 — LLM Wiki 3-레이어 방식(Ingest/Query/Lint) 도입

## [2026-05-08] lint | 잘못 배치된 파일 4개 재이동
- 일본 방문 등록.md (비번 포함) → Locker/
- 미국 출장 교훈.md, 해외 출장 준비물.md → 일상 생활/여행/
- 외화 관련.md → Investing/

## [2026-05-08] lint | 볼트 루트 Exported image 고아 파일 136개 삭제
- 전체 264개 중 노트 미참조 고아 136개 삭제
- 참조된 128개 (png/jpeg/tiff/octet-stream) 유지

## [2026-05-08] ingest | OneNote → Obsidian 이전 완료
- 삭제: 쇼핑아이템/ 211개 (구버전 위시리스트)
- 이동 405개: IT 팁(204) → IT tips/, Remember(54) → Locker/OneNote-Remember/
- 신설 폴더: 일상 생활/{요리,자동차,통신사,여행,평창,기타}, 인천스카이뷰/이사/
- Blog/ +9개, SND/Accounts/ +3개, To-Do List/ +3개, 일상 생활/ +1개(동건 군대)
- OneNote/ 폴더 완전 삭제
- MOC 업데이트: Blog, 일상 생활, IT tips, 인천스카이뷰, To-Do List, HOME.md

## [2026-05-08] lint | SKT 인터넷 재약정 파일 통합 및 이동
- 삭제: 일상 생활/통신사/SKT인터넷 약정.md (중복, 내용 전부 위키에 포함)
- 이동: 일상 생활/SKT 집 인터넷 재약정.md → 일상 생활/통신사/SKT 집 인터넷 재약정.md

## [2026-05-08] ingest | SKT 인터넷 재약정 쿠폰 수령 문자 (2026-04-22)
- 네이버페이 포인트 쿠폰 40,000원, 교환 유효기간 2027-04-21
- SKT 집 인터넷 재약정.md 업데이트

## [2026-05-08] lint | 볼트 전체 재구성 실행
- 루트 정리: index.md 삭제, SCHEMA.md → raw/ 아카이브, log.md 통합
- 2026-05-01.md → 2026/05/26.05.01 Fri.md 이동
- 외부 회의실 사용시.md → SND/ 이동
- 신규 폴더: AI/, SND/회의/, 2026/05/
- 분류전/ 5개 노트 분류: 미드→일상생활, AI Tech Briefing×2→AI/, Contacts→Career/, 예스24 회의록→SND/회의/
- SND/: 중복 Paperclip.md 통합, Untitled.md 삭제, 회의_20251028.md→SND/회의/
- CLAUDE.md 보강 (SCHEMA.md 파일명 컨벤션·페이지타입·임계값 흡수)
- HOME.md 업데이트

## [2026-05-08] query | OneNote General Stuff 노트북 이전 완료 확인
- 14개 섹션 전부 처리됨: 13개 이전, 쇼핑아이템·Action Plan 2개는 오래된 내용으로 사용자가 삭제
- 누락 섹션 없음

## [2026-05-09] lint | 볼트 이미지 구조 정리
- 볼트 위치 변경: iCloud → /Users/marksnd/Documents/MainVault (CLAUDE.md 업데이트)
- 삭제: SND/Accounts/우리카드(법인).md (정보 불필요, 사용자 요청)
- 이동: 루트 이미지 123개 → _attachments/ 폴더 신설 후 이동
- 링크 변환: 85개 노트의 ![](Exported%20image%20...) → ![[Exported image ...]] (Obsidian 위키링크)
- Obsidian 첨부파일 기본 경로: app.json → attachmentFolderPath: "_attachments"

## [2026-05-09] lint | 비정상 확장자 이미지 6개 교정
- octet-stream 4개: 실제 JPEG/PNG 확인 후 올바른 확장자로 변환 → _attachments/ 이동
- tiff 2개: sips로 PNG 변환 → _attachments/ 이동 (Obsidian TIFF 미지원)
- 참조 노트 6개 링크 업데이트 (Blog, To-Do List×3, IT tips×2)

## [2026-05-09] lint | 2024 일기 전체 삭제
- 삭제: 2024/ 폴더 전체 (일기 117개 + MOC + 월별 서브폴더 8개)
- 사유: 마크쌤 판단 — 재활용 가치 없음
- HOME.md에서 2024 Journal 항목 제거
