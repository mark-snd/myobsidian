# Wiki Schema

## Domain
개인 지식 관리(PKM) 및 회사 업무 기억 — 일상에서 배운 것, 회사에서 기억해야 할 것, IT/개발/투자 지식, 커리어 관련 인사이트를 누적·연결한다.

## Conventions
- 파일명: 소문자, 하이픈, 공백 없음 (예: `transformer-architecture.md`, `snd-project-onboarding.md`)
- 모든 wiki 페이지는 YAML frontmatter로 시작
- `[[wikilinks]]`로 페이지 간 연결 (페이지당 최소 2개 outbound link)
- 페이지 업데이트 시 `updated` 날짜 갱신
- 새 페이지는 반드시 `index.md`의 해당 섹션에 추가
- 모든 작업은 `log.md`에 append

## Frontmatter
```yaml
---
title: 페이지 제목
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [태그분류 아래 목록에서 선택]
sources: [raw/articles/source-name.md]
---
```

## Tag Taxonomy
새 태그는 반드시 여기에 먼저 추가한 뒤 사용. 이 목록 외의 태그 사용 금지.

### 업무 (Work)
- `project` — 회사 프로젝트, 업무 단위
- `meeting` — 회의록, 결정사항
- `client` — 고객사, 파트너
- `process` — 사내 프로세스, 절차, 규칙
- `colleague` — 함께 일하는 사람
- `deadline` — 일정, 마일스톤

### 지식 (Knowledge)
- `concept` — 개념, 이론, 프레임워크
- `tool` — 소프트웨어, 서비스, 도구
- `technique` — 방법론, 실무 기법
- `reference` — 참고자료, 문서, 링크
- `ai` — AI/ML 관련
- `dev` — 개발, 코딩

### 개인 (Personal)
- `career` — 커리어, 성장, 역량
- `finance` — 투자, 재테크, 금융
- `learning` — 공부, 독서, 강의
- `goal` — 목표, 계획
- `life` — 일상, 루틴, 건강

### 메타 (Meta)
- `comparison` — 비교 분석
- `timeline` — 시간순 정리
- `summary` — 요약, 정리
- `question` — 미해결 질문, 탐색 중인 주제
- `person` — 인물 (동료, 업계 인물 등)
- `org` — 조직, 회사, 팀

## Page Thresholds
- **페이지 생성**: 2개 이상의 소스에서 언급되거나, 한 소스에서 핵심적으로 다루는 경우
- **기존 페이지에 추가**: 이미 다루는 내용이 소스에 등장하는 경우
- **페이지 생성 안 함**: 스쳐 지나가는 언급, 도메인 밖의 내용
- **페이지 분할**: 200줄 초과 시 — 소주제로 분리 + 상호 링크
- **페이지 보관**: 완전히 대체된 내용 → `_archive/`로 이동, index에서 제거

## Entity Pages
인물, 조직, 프로젝트, 도구 등 고유한 대상 하나당 한 페이지.
- 개요 / 무엇인지
- 핵심 사실과 날짜
- 관련 엔티티와의 관계 (`[[wikilinks]]`)
- 출처 참조

## Concept Pages
개념, 기법, 프레임워크 하나당 한 페이지.
- 정의 / 설명
- 현재 이해 수준
- 열린 질문이나 논쟁점
- 관련 개념 (`[[wikilinks]]`)

## Comparison Pages
둘 이상을 나란히 분석.
- 비교 대상과 이유
- 비교 기준 (테이블 형식 권장)
- 결론 또는 종합
- 출처

## Update Policy
새 정보가 기존 내용과 충돌할 때:
1. 날짜 확인 — 최신 출처가 일반적으로 우선
2. 진짜 모순이면 양쪽 주장을 날짜·출처와 함께 병기
3. frontmatter에 `contradictions: [page-name]` 표시
4. lint 보고서에서 사용자 검토 요청
