# CLAUDE.md

Claude Code가 이 프로젝트를 작업할 때 항상 참고하는 프로젝트 지침서입니다.

---

## 프로젝트 개요

이 레포지토리는 Claude Code 설정 모음입니다.
- `.claude/agents/` — 자율 실행 에이전트
- `.claude/commands/` — 슬래시 커맨드
- `.claude/skills/` — 도메인 지식 베이스
- `.claude/settings.json` — 전역 권한 설정

---

## 작업 원칙

### 코드 작성 시
- 한국어 주석을 우선으로 작성할 것
- 변수명/함수명은 영어로 작성할 것 (camelCase)
- 파일 수정 전에 반드시 현재 내용을 먼저 읽을 것

### 문서 작성 시
- Markdown 파일은 항상 한/영 병기로 작성할 것
- 섹션마다 `---` 구분선을 사용할 것
- 테이블은 가능한 한 활용할 것

### 에이전트/커맨드/스킬 작성 시
- `.md` 파일 상단에 frontmatter(description, argument-hint) 포함할 것
- 각 파일의 역할과 사용 시점을 명확히 명시할 것
- 재사용 가능하도록 `$ARGUMENTS` 변수를 적극 활용할 것

---

## 금지 사항

- 확인 없이 파일을 삭제하지 말 것
- 테스트 없이 대규모 리팩토링을 진행하지 말 것
- 민감한 정보(API 키, 비밀번호)를 파일에 직접 기록하지 말 것

---

## 참고 링크

- [Claude Code 공식 문서](https://docs.anthropic.com/claude-code)
- [참고 레포: chacha95/claude-code-harness](https://github.com/chacha95/claude-code-harness)
