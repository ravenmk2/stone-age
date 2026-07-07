# Project documentation model

The project MUST maintain this `docs/` tree:

```txt
docs/
├── README.md              # one-line project description + doc index
├── constitution.md        # project charter
├── glossary.md            # global glossary
├── architecture.md        # global architecture + tech stack (split into architecture/ when large)
├── conventions.md         # conventions (split into conventions/ when large)
├── adr/
│   ├── index.md           # lists only effective decisions
│   └── NNN-<slug>.md      # architecture decisions (append-only)
├── contracts/
│   ├── api.md             # API doc for external systems (language/tech-agnostic)
│   └── <slug>.md          # contracts for external systems, e.g. events.md
├── experience/
│   ├── pitfalls.md        # common mistakes
│   └── <slug>.md
├── specs/
│   ├── <slug>.md          # global requirements specs
│   └── <domain>/<slug>.md # per-domain requirements specs
├── design/
│   ├── <slug>.md          # global high level system design
│   └── <domain>/<slug>.md # per-domain high level design, e.g. payment/db-schema.md
├── plans/
│   ├── active/
│   │   └── YYYY-MM-DD-<slug>/
│   │       ├── plan.md    # mandatory: Why + What + doc changes + deviations
│   │       ├── spec.md    # incremental requirements spec (merged into docs/specs/ when complete)
│   │       ├── design.md  # technical design, How (optional; required for greenfield; merged into docs/design/ when complete)
│   │       └── tasks.md   # decomposed dev tasks
│   └── completed/         # archived plans
└── references/            # external knowledge — user-maintained only
    ├── <slug>.md
    └── <domain>/<slug>.md
```

`AGENTS.md` at the repo root emphasizes `docs/constitution.md` — the project charter (purpose, principles, invariants) that governs all work — and points to `docs/README.md` for the documentation index.
