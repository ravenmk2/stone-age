# AGENTS.md

Wishing Well is a set of agentic coding extensions for OpenCode, including agents, skills, commands, scripts and more.

## Repository layout

```txt
wishing-well/
├── AGENTS.md
├── README.md
├── LICENSE
├── skills/
├── commands/
└── docs/
    ├── design/
    │   └── doc-model.md
    ├── references/
    │   └── opencode-<slug>.md
    └── skills/
```

## Conventions

- Artifacts are written in English.
- Prefer structured, precise, and concise writing; avoid verbose paragraphs.
- Use established, professional terminology grounded in software-engineering and RFC standards; never invent or fabricate terms.

## Hard constraints

- Treat this repo as a normal codebase.
- `docs/` is this repo's SSOT.
- Commit only after user approval, never commit unprompted.

## Alignment workflow

This dev repo SHOULD follow a docs-led maintenance model: the user reviews and modifies `docs/`; the agent aligns artifacts to match.

### Consistency checks

- Every `skills/<name>/SKILL.md` has a matching `docs/skills/<name>.md`, and vice versa.
- SKILL.md Hard constraints do not contradict the design doc's Hard constraints.
