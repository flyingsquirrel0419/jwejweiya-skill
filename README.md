# jwejweiya

한국 커뮤니티 밈 "줴줴이야" 감탄사 세트로 답하는 말투 스킬.

"줴줴이야"는 말투가 아니라 감탄사 하나다. 뜻은 "끝났다, 망했다". 이 스킬은 그 감탄사들과 주변 표현(예?, 엄.., 아뇨아뇨아뇨, 티~원, 요이~, 진~지?, 지~랄)을 앞뒤에 몰아넣고, 가운데 본론만 또렷하게 남긴다.

## 답의 구조

1. 앞 반응 1~3줄 — 예? / 엄... / 아뇨아뇨아뇨 / 진~지?
2. 본론 1~2줄 — 감탄사 없이 커뮤 반말로 핵심 하나
3. 꼬리 1줄 — 감탄사 3~6개

```
예?
진~지?
3시간은 아직 아무 의미 없음
여기서 또 보내면 그게 진짜 망하는 각임 걍 폰 내려놔라
엄.. 아 줴줴이야~ 티~원
```

## 언제 쓰나

사용자가 명시적으로 요청할 때만 쓴다. ("줴줴이야로 말해", "그 감탄사 세트로 답해", "커뮤 말투로 매운맛")

일반 대화, 정보 답변, 진지한 상담에는 적용하지 않는다.

- "그만" → 즉시 평범한 말투
- "순하게" → 앞 반응 1줄 + 본론 1줄 + 꼬리 1줄
- "자세히" → 본론만 늘림
- 무거운 얘기 → 3단 구조까지 끄고 평범하게

## 설치

한 군데에 받아두고 각 CLI 스킬 폴더에 링크하는 게 제일 편하다. `SKILL.md` 형식은 아래 CLI들이 전부 같이 읽는다.

```bash
git clone https://github.com/flyingsquirrel0419/jwejweiya-skill.git ~/skills/jwejweiya

for d in ~/.claude/skills ~/.codex/skills ~/.config/opencode/skills ~/.pi/agent/skills ~/.gemini/skills; do
  mkdir -p "$d"
  [ -e "$d/jwejweiya" ] || ln -s ~/skills/jwejweiya "$d/jwejweiya"
done
```

심볼릭 링크가 안 되는 환경(윈도우 등)이면 폴더째 복사하면 된다.

```bash
cp -r ~/skills/jwejweiya ~/.codex/skills/jwejweiya
```

### CLI별 경로

| CLI | 개인 스킬 | 프로젝트 스킬 |
|---|---|---|
| Claude Code | `~/.claude/skills/<name>/` | `.claude/skills/<name>/` |
| Codex CLI | `~/.codex/skills/<name>/` | `.codex/skills/<name>/` |
| opencode | `~/.config/opencode/skills/<name>/` | `.opencode/skills/<name>/` |
| Pi | `~/.pi/agent/skills/<name>/` | `.pi/skills/<name>/` |
| Gemini CLI | `~/.gemini/skills/<name>/` | `.gemini/skills/<name>/` |

opencode는 `~/.claude/skills/`와 `~/.agents/skills/`도 같이 읽으니, Claude Code에만 넣어도 자동으로 잡힌다. Gemini CLI도 `~/.agents/skills/`를 별칭으로 본다.

### 설치 확인

```bash
gemini skills list
```

opencode는 실행 후 skill 목록에 `jwejweiya`가 뜨면 된다. 안 뜨면 `SKILL.md` 대문자 표기와 frontmatter의 `name`·`description`부터 확인.

### 프로젝트에만 넣기

레포 안에서만 쓰고 싶으면 프로젝트 경로에 넣는다.

```bash
mkdir -p .claude/skills
cp -r ~/skills/jwejweiya .claude/skills/jwejweiya
```

## 구성

- `SKILL.md` — 스킬 본문. 표현 사전, 강도 조절, 표기 규칙, 금지 목록, 예시
- `LICENSE` — MIT

## 라이선스

MIT
