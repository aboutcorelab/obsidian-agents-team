```
Obsidian Vault 안에서의 노트 관리, 인사이트 추출 등을 하는 Agent Team을 구축합니다.
Agent Team은 반드시 Claude 공식 가이드라인을 따라야 합니다.
- https://code.claude.com/docs/en/sub-agents
- https://code.claude.com/docs/en/skills

## 요구사항
### inbox 관리
1. 00 inbox에 있는 모든 노트들을 분석해서 제텔스카스텐 기법에 맞게 노트를 분리 
2. 각 노트는 독립적인 제목을 가져야 하며, 내용은 한 가지 핵심 개념만 포함
3. 노트는 obsidian에서 활용할 수 있도록 markdown 파일 형태로 분리하고 출력 할 것
2. 분리된 노트들은 03 resource 폴더로 바로 이동

### Note Connection
1. 03 resource 에 있는 파일들을 모두 읽어서 아래 [제텔스카스텐 노트 연결 요구사항]을 기반으로 서로 연결을 할 것

[제텔스카스텐 노트 연결 요구사항]
1. 연결은 단순한 '관련 있음' 표시가 아니라, 노트 간의 대화, 반박, 지지, 확장 등 명확한 **맥락(Context)**을 포함해야 한다.
2. 링크를 삽입할 때는 [[링크]]만 남기지 말고, **왜 이 노트를 연결하는지 설명하는 문장(Bridge Text)**을 반드시 함께 작성해야 한다.
3. 연결되는 대상은 문서 전체가 아닌, 하나의 분명하고 원자적인 아이디어(Atomic Idea) 단위여야 한다.
4. 연결된 노트(타겟)를 열어보지 않고도 현재 노트의 내용만으로 문맥이 이해되도록 **독립적인 완결성(Autonomy)**을 갖춰야 한다.
5. 노트 제목은 연결된 문장 속에서 자연스럽게 읽힐 수 있도록 서술형이나 명확한 명사구로 작성되어야 한다.
6. 동일한 주제 내의 연결(직렬 연결)뿐만 아니라, 서로 다른 주제 간의 **이질적 연결(Cross-pollination)**을 통해 새로운 통찰을 유도해야 한다.
7. 개별 노트들이 쌓이면 이를 상위에서 조망하고 연결 흐름을 정리해 주는 **구조 노트(Structure Note/MOC)**를 생성해야 한다.
8. 연결은 하향식(Top-down) 분류가 아닌, 개별 노트에서 시작해 군집(Cluster)을 형성하는 상향식(Bottom-up) 방식으로 이루어져야 한다.
9. 노트 작성 시 **백링크(Backlink)**를 주기적으로 확인하여, 과거의 노트가 현재의 아이디어와 어떻게 연결될 수 있는지 재검토해야 한다.

### Insight 생성
1. 03 resource 폴더에 있는 모든 노트를 읽어서 서로 연관이 있거나 인사이트를 발굴
2. 제텔스카스텐 메모법을 기반으로 노트간의 연관성 새로운 발견 등을 통해서 인사이트를 발굴
3. 발굴된 인사이트 들은 obsidian에서 활용할 수 있도록 markdown 형태로 출력
4. 인사이트 들은 참고한 노트들을 기본적으로 링크로 가지고 있어서 연결성을 볼 수 있도록 할 것
5. 인사이트 들은 출력해서 99 draft 로 모두 이동할 것
6. 똑같은 인사이트 발굴을 하지 않기 위해서 .insight.md 파일을 만들어 관리하고 해당 파일에 추출한 인사이트를 리스트업해서 향후 똑같은 인사이트들이 중복으로 뽑히지 않도록 할 것

### Blog 글 작성
1. Blog 글을 작성하는 방법은 크게 두가지로 작성할 수 있도록 Command를 구성 할 것 (createblog_by_draft, createblog_by_notes)
2. createblog_by_draft 는 나의 초안을 기반으로 참조 파일들의 정보를 가지고 보강하여 blog 글을 작성하는 명령, 옵션으로 --draft "{나의 초안 파일 위치}" --ref "{reference_file_1}, {reference_file_2} ..." 제공, 나의 초안의 내용을 우선적으로 포함하여 내용이 전개 되도록 할 것
3. createblog_by_notes 는 여러 레퍼런스 파일들의 정보를 종합하여 글을 작성하는 것으로 여러 레퍼런스를 입력받아 동작 할 수 있도록 함
4. 모든 Blog 작성은 '나의 글쓰기 어투 및 스타일' 을 기반으로 작성하여 일관 된 톤 앤 매너의 Blog를 작성할 수 있도록 해야함. '나의 글쓰기 어투 및 스타일' 파일을 참조 할 수 있도록 할 것 
5. 모든 Blog 작성은 SEO, GEO에 최적화 된 글쓰기를 해야함
6. 생성 된 Blog 글은 obsidian에 활용할 수 있도록 markdown 파일 형식으로 출력 할 것
7. 나의 초안을 기반으로 만든 blog는 나의 초안 파일을 출력으로 대체 하도록 할 것
8. 여러 파일을 참고하여 만든 blog는 99 draft 에 출력되도록 할 것

### Blog Thumbnail 작성 
1. Blog 파일을 기반으로 Thumbnail을 작성 
2. 파일의 제목을 반드시 포함하고 부제를 생성해서 같이 썸네일에 포함되도록 할 것
3. "@aboutcorelab"을 포함하여 생성할 것 작성자 느낌으로 워터마크처럼 표현할 것
4. Nanobanana Pro 모델을 활용할 것 Gemini API를 활용하여 동작 할 것

## Agent 구성
- obsidian-team-leader.md
  -- 전체 플로우를 Orchestration 하는 팀 리더 역할
  -- inbox 관리, 노트 연결, 인사이트 생성, Blog 글 작성 agent에게 작업을 나눠 주고 전체 흐름을 관리
- inbox-manage-agent.md ← inbox를 관리하는 agent
- note-connection-agent.md ← resource 폴더 내 노트들을 연결하고 관리하는 agent
- insight-agent.md ← insight 생성 agent
- blog-writer-by-draft-agent.md ← draft를 기반으로 blog글을 생성하는 agent
- blog-writer-by-notes-agent.md ← 여러 레퍼런스 파일들을 기반으로 blog글을 생성하는 agent

## Claude Code 스킬 구조 (공식 가이드라인)
반드시 아래 구조를 따라야 해:

.claude/skills/
├── generate-thumbnail/
    └── SKILL.md     ← YAML frontmatter 필수

각 SKILL.md는 이 형식을 따라:
---
name: skill-name
description: 스킬 설명 + 사용 시점
allowed-tools:
  - Bash
  - Read
  - Write
---

## 전체 구조
- Python 모듈: ./claude/src/obsidian-team/
- 스킬: .claude/skills/{skill-name}/SKILL.md
- 에이전트: .claude/agents/{agent-name}.md
- 커맨드: .claude/commands/{command}.md
- 설정: .claude/settings.json

각 모듈은 독립 테스트 가능하게,
스킬/에이전트는 SKILL.md에 사용법 문서화해줘.
```

---

## 팁

### 모델 고정하기
```
이미지 생성 모델을 gemini-3-pro-image-preview로 고정해.
```

### Claude Code 스킬 구조 체크리스트
```
스킬 만들 때 이 체크리스트 확인해:
☐ .claude/skills/{skill-name}/ 폴더 생성
☐ 폴더 안에 SKILL.md 파일 생성 (파일명 정확히)
☐ YAML frontmatter에 name, description, allowed-tools 포함
☐ description에 "언제 사용하는지" 명시
☐ Instructions, Usage, Config 섹션 포함
☐ .claude/settings.json에 스킬 등록
```

### 점진적 빌드
복잡한 시스템은 한 번에 만들지 말고:
1. 먼저 Python 모듈 → 테스트
2. 스킬 폴더 구조 생성 → SKILL.md 작성
3. 에이전트 정의 → 스킬 연결
4. 커맨드 → 통합 테스트
5. settings.json 업데이트

### 디버깅
```
에러 나면 각 단계별로 출력 보여줘.
중간 파일들 삭제하지 마.
```

### SKILL.md 예제 템플릿
```markdown
---
name: my-skill
description: 이 스킬의 설명. OO할 때, XX가 필요할 때 사용하세요.
allowed-tools:
  - Bash
  - Read
  - Write
---

# My Skill

설명...

## Instructions

1. 단계 1
2. 단계 2
3. 단계 3

## Usage

\`\`\`python
from src.module import MyClass
instance = MyClass()
instance.do_something()
\`\`\`

## Config

| 항목 | 값 |
|------|-----|
| 모델 | model-name |
| 옵션 | value |

## Features

1. **feature_1**: 기능 설명
2. **feature_2**: 기능 설명
```
