# Echo Obsidian 요청 처리 흐름

작성일: 2026-05-08
분류: OpenClaw / Echo / Obsidian / 런타임 구조

## 한 줄 요약

Telegram에서 마크쌤이 옵시디언 관련 요청을 보내면, OpenClaw Gateway가 Telegram 업데이트를 Echo 에이전트로 라우팅하고, Echo가 `obsidian-vault` 스킬의 `obsidian.py`를 subprocess로 실행해 iCloud Drive의 Obsidian Vault를 검색/읽기/수정한 뒤 결과를 한국어로 정리해 다시 Telegram으로 응답한다.

## 전체 흐름

### 1. Telegram 요청

예시:

> 정관 관련 노트 찾아줘

- 마크쌤이 Telegram에서 요청
- Telegram Bot API를 통해 `@unclemark_clawd_bot`으로 전달

### 2. OpenClaw Gateway

- LaunchAgent: `ai.openclaw.gateway`
- Gateway 포트: `18789`
- 실행 위치: `/opt/homebrew/.../openclaw`
- Telegram plugin이 update 수신
- `openclaw.json` 설정에 따라 라우팅
  - `channels.telegram.accounts.default`
  - `bindings`
  - agent: `echo`
  - workspace: `/Users/mark/.openclaw/workspace`

### 3. Echo agent

- 모델: `openai-codex/gpt-5.5`
- workspace context 로드:
  - `SOUL.md`
  - `AGENTS.md`
  - `TOOLS.md`
  - `MEMORY.md`
  - 최근 `memory/*.md`
- workspace local skill 탐색:
  - `/Users/mark/.openclaw/workspace/skills/local/`
- `obsidian-vault/SKILL.md` 설명에 따라 옵시디언 검색/읽기/생성/수정 요청인지 판단

실행 예시:

```bash
python3 /Users/mark/.openclaw/workspace/skills/local/obsidian-vault/scripts/obsidian.py search "정관"
```

### 4. obsidian.py 실행

`obsidian.py`는 Echo 프로세스가 Bash/subprocess로 호출하는 별도 Python 프로세스다.

주요 동작:

- vault path를 `config.json`에서 읽음
- 또는 `$OBSIDIAN_VAULT_PATH` 환경변수로 override 가능
- `pathlib.rglob("*.md")`로 Vault 내 markdown 노트 탐색
- 지원 subcommand:
  - `folders`
  - `search`
  - `read`
  - `create`
  - `append`
  - `replace`
  - `recent`
- `resolve_note()`가 Vault 밖으로 경로가 빠져나가지 않도록 path escape 방지
- 결과는 JSON으로 stdout에 반환

### 5. iCloud Drive Obsidian Vault

현재 Vault 위치:

```text
/Users/mark/Library/Mobile Documents/iCloud~md~obsidian/Documents/MainVault
```

중요한 운영 특성:

- iCloud Drive는 파일이 로컬에 없으면 placeholder 상태일 수 있음
- macOS FileProvider가 파일을 읽을 때 실제 내용을 materialize/download함
- TCC 권한이 접근을 막을 수 있음
- 특히 `python3.14`에 Full Disk Access가 없으면 읽기 실패 가능
- 오늘 이전에 옵시디언 노트 읽기가 깨졌던 지점이 바로 이 구간이었음

대표 오류:

```text
Resource deadlock avoided
Operation not permitted
compressed,dataless
isDownloaded = 0
```

해결 방향:

- 해당 노트를 Finder/Obsidian에서 한 번 열어 iCloud 원문 다운로드 유도
- Python 실행 바이너리 또는 OpenClaw 관련 프로세스에 Full Disk Access 부여
- FileProvider 상태 확인

### 6. Echo 응답 생성

Echo는 `obsidian.py`가 반환한 JSON을 파싱한다.

필요하면 후속 호출을 체인으로 이어간다.

예:

1. `search "정관"`
2. top hit 확인
3. `read "SND/정관 변경.md"`
4. 중요 표시/핵심 문장 추출
5. 한국어로 요약

응답 원칙:

- 마크쌤의 현재 언어에 맞춰 한국어로 응답
- Telegram-friendly 포맷 사용
- DM에서는 별도 message tool 없이 plain text로 답하면 Gateway가 원래 채팅으로 자동 라우팅

## 핵심 아키텍처 포인트

- Telegram 요청은 Gateway를 통해 Echo agent로 라우팅된다.
- Echo는 직접 Obsidian 앱을 조작하는 것이 아니라, Vault의 markdown 파일을 파일시스템으로 읽고 쓴다.
- 실제 Obsidian 작업은 `obsidian-vault/scripts/obsidian.py`가 담당한다.
- iCloud/FileProvider/TCC 권한 상태가 옵시디언 접근 성공 여부를 좌우한다.
- 노트 삭제는 기본 동작이 아니며, 명시 지시 없이는 하지 않는다.
- 검색 → 읽기 → 요약/수정 → 응답의 구조로 동작한다.

## 나중에 찾아볼 키워드

- Echo Obsidian 요청 처리 흐름
- OpenClaw Gateway Telegram routing
- obsidian-vault skill
- obsidian.py
- iCloud Drive FileProvider
- TCC Full Disk Access
- Resource deadlock avoided
- Operation not permitted
- compressed,dataless
- 정관 노트 검색 오류

---

## 추가 메모: Skill 실행 구조와 권한/범위

작성일: 2026-05-08 06:37 KST
출처: Mark 설명 메모

### Skill은 library가 아니라 subprocess

OpenClaw skill은 Node Gateway에 직접 import되는 library가 아니다.

Echo 모델이 Bash tool을 통해 다음처럼 별도 프로세스를 실행한다.

```bash
python3 obsidian.py ...
```

이 구조의 의미:

- skill은 Gateway/Node 런타임과 분리되어 있다.
- Python뿐 아니라 어떤 언어로도 skill을 만들 수 있다.
- 대신 macOS TCC 권한은 실행 binary별로 평가된다.
- 그래서 `node`에 Full Disk Access를 줘도 Obsidian Vault 접근 문제가 해결되지 않았다.
- 실제 Vault 접근은 `python3.14`가 했기 때문에, `python3.14`에 Full Disk Access를 줘야 해결됐다.

### Skill discovery는 filesystem 기반

Gateway는 다음 위치를 스캔한다.

```text
workspace/skills/local/*/SKILL.md
```

유효한 YAML frontmatter가 있는 `SKILL.md`를 발견하면 Echo의 system prompt에 노출한다.

특징:

- 별도 registration 단계가 없다.
- 새 skill folder를 넣으면 discovery 대상이 된다.
- 원칙적으로 restart 없이 반영되는 구조다.

### Vault path는 config-over-code

Vault 위치는 코드에 박혀 있지 않고 `config.json`에 있다.

```text
skills/local/obsidian-vault/config.json
```

운영 원칙:

- Vault를 옮기면 `config.json` 한 곳만 수정하면 된다.
- 테스트 시에는 환경변수로 override할 수 있다.

```bash
OBSIDIAN_VAULT_PATH=/path/to/vault python3 obsidian.py ...
```

### Safety는 script가 아니라 SKILL.md에 있다

`obsidian.py` 자체는 현재 delete command를 노출하지 않는다.

하지만 “삭제는 명시 지시 없이는 하지 않는다”는 규칙은 코드의 hard guard가 아니라, Echo가 `SKILL.md`의 한국어 safety clause를 읽고 따르는 model-level soft guardrail이다.

구분:

- Soft guardrail: `SKILL.md`의 삭제 금지/주의 규칙
- Hard guardrail: `resolve_note()`의 path escape 방지

즉, Vault 밖 경로 접근 방지는 코드에서 강제되지만, 삭제 관련 운영 원칙은 모델 행동 규칙에 가깝다.

### Persistent index는 없다

현재 Obsidian 검색은 persistent index를 쓰지 않는다.

동작 방식:

- 매번 Vault 전체를 다시 스캔한다.
- 수백 개 노트 규모에서는 충분히 빠르다.
- 노트가 수천 개 이상으로 커지면 별도 index가 필요할 수 있다.

### Echo는 skill data에 대해 turn 단위 stateless

Skill output은 자동 캐시되지 않는다.

의미:

- 같은 대화 안에서 같은 노트를 다시 보려면 Echo가 다시 `read`를 호출한다.
- turn을 넘긴 장기 기억은 자동 생성되지 않는다.
- cross-turn memory는 Echo가 직접 `workspace/memory/*.md`에 요약해서 남긴다.
- skill output이 자동으로 memory로 들어가는 구조는 아니다.

### Skill scope는 workspace 단위

현재 Obsidian Vault 접근 skill은 기본 Echo workspace에만 있다.

즉, 다음 에이전트들은 이 Vault를 볼 수 없다.

- Carol
- Duckgeun
- Andy
- April
- Slack-Bolt

이유:

- skills는 workspace-scoped다.
- 해당 skill folder를 다른 workspace에 복사하지 않았기 때문이다.
- 이는 의도된 격리 설계다.

## 운영상 중요한 결론

- Obsidian 접근 문제를 볼 때는 Gateway/Node 권한만 보지 말고 실제 실행 binary인 `python3.14`의 TCC/FDA 권한을 확인해야 한다.
- Skill 추가/변경은 `workspace/skills/local/*/SKILL.md` 파일 배치가 핵심이다.
- Vault 이전 시에는 code가 아니라 `config.json`을 수정한다.
- 삭제 안전은 현재 hard enforcement가 아니라 model policy에 가까우므로, 위험 작업은 계속 명시 확인 후 진행해야 한다.
- 검색 성능 문제가 생기면 persistent index 도입을 검토한다.
- 다른 에이전트가 Obsidian을 못 보는 것은 오류가 아니라 workspace-scoped isolation 때문이다.

