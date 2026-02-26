# claude-code-setup

> Claude Code를 위한 **agents, commands, skills** 설정 모음입니다.  
> My personal Claude Code configuration with reusable agents, slash commands, and skills.

---

## 📁 폴더 구조

```
claude-code-setup/
├── .claude/
│   ├── agents/          # 자율 실행 에이전트 (복잡한 작업용)
│   ├── commands/        # 슬래시 커맨드 (/명령어)
│   ├── skills/          # 도메인별 지식 베이스
│   └── settings.json    # Claude Code 전역 설정
├── CLAUDE.md            # 프로젝트 전체 지침서
└── README.md
```

---

## 🤖 Agents

복잡하고 긴 작업을 Claude가 자율적으로 처리하도록 돕는 전문 에이전트 모음입니다.  
각 `.md` 파일을 `.claude/agents/` 폴더에 복사하면 바로 사용 가능합니다.

| 에이전트 | 역할 |
|---|---|
| `code-reviewer` | 코드 품질 및 아키텍처 리뷰 |
| `doc-writer` | 기술 문서 및 README 자동 작성 |
| `bug-fixer` | 에러 탐지 및 자동 수정 |
| `planner` | 작업 계획 수립 및 태스크 분해 |

---

## ⚡ Commands

`/명령어` 형태로 Claude Code에서 바로 실행할 수 있는 슬래시 커맨드입니다.

| 커맨드 | 역할 |
|---|---|
| `/dev-plan` | 개발 계획 문서 자동 생성 |
| `/dev-review` | 코드 리뷰 및 개선안 제안 |

---

## 🧠 Skills

Claude가 특정 맥락(파일 타입, 폴더 등)을 감지하면 자동으로 불러오는 도메인 지식입니다.

| 스킬 | 역할 |
|---|---|
| `nextjs-guidelines` | Next.js 개발 패턴 및 베스트 프랙티스 |
| `python-guidelines` | Python 코딩 스타일 가이드 |
| `writing-guidelines` | 기술 문서 작성 가이드 |

---

## 🚀 사용법

1. 이 레포를 클론합니다.
```bash
git clone https://github.com/ochirii/claude-code-setup.git
```

2. `.claude` 폴더를 프로젝트 루트에 복사합니다.
```bash
cp -r claude-code-setup/.claude /your-project/
```

3. Claude Code를 실행하면 설정이 자동으로 적용됩니다.

---

## 📝 참고

- [Claude Code 공식 문서](https://docs.anthropic.com/claude-code)
- [chacha95/claude-code-harness](https://github.com/chacha95/claude-code-harness) — 이 레포의 참고 소스
