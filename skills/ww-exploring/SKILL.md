---
name: ww-exploring
description: Convergent research — refine a rough idea into a scoped conclusion.
---

# Exploring

Refine a roughly-formed idea into a scoped conclusion — align on requirements and scope with the user, then route. Produces a scope conclusion; no file artifact.

## When to use me

Use when the user already has a rough idea but it needs convergence: align scope, resolve ambiguity, decide what's in and out. Invoke when the direction is clear enough to converge but the boundaries aren't. Do NOT use to brainstorm divergent alternatives (use `ww-brainstorming`), diagnose a bug/perf issue (use `ww-analyzing`), write a Plan (use `ww-planning`), or write docs directly (use `ww-writing-doc`). Skip when the goal/scope is already clear.

## Workflow

```mermaid
flowchart TD
    A[1. Explore project] --> B[2. Restate + determine work-type]
    B --> C{Aligned?}
    C -- No --> D[3. Clarify one question at a time]
    D --> B
    C -- Yes --> E[4. Produce scope conclusion + routing]
    E --> F[5. Self-review]
    F --> G{Skip?}
    G -- No --> H[Review & fix]
    G -- Yes --> I[6. User review]
    H --> I
    I --> J{Approved?}
    J -- changes --> E
    J -- approved --> K[7. Hand off or stop]
    K --> L{Route}
    L -- documentation --> M[Load ww-writing-doc]
    L -- development --> N[Load ww-planning]
    L -- stop --> O([Stop])
```

Follow these steps in order.

### 1. Explore the project

Read `AGENTS.md` (foregrounds `docs/constitution.md` and points to `docs/README.md`) → `docs/README.md`, then the relevant docs (`constitution.md`, `architecture.md`, `conventions.md`, `glossary.md`, `specs/`, `design/`, `contracts/`, `adr/`, and `references/` as context) and code. Build a picture of what the project is and how the user's intent fits.

### 2. Restate and determine work-type

Restate the situation to the user and determine the work type for routing: **documentation** (refinement lands as spec / domain design) or **development** (the idea will be implemented). The research mode is exploring (convergent); only the work-type is open.

### 3. Clarify one question at a time

Use the `question` tool to resolve ambiguity, ONE question at a time — let each answer shape the next. Stop once you and the user share the same understanding.

### 4. Produce scope conclusion and routing

Produce the conclusion: refined scope (in/out), requirements where useful, plus intended doc changes (specs / domain design) if any. Route:

- **documentation** → `ww-writing-doc`.
- **development** → `ww-planning`.

### 5. Self-review

Ask via `question` whether to skip self-review (`yes` / `no`). If `no`, check against the [Self-review checklist](#self-review-checklist), fix in place, then summarize.

### 6. User review — HARD-GATE

Present the conclusion and routing for user review. You MUST NOT proceed until the user explicitly approves. On requested changes, update and re-present. Loop until approval.

### 7. Hand off or stop

On approval, hand off to the routed skill (`ww-writing-doc` or `ww-planning`) via `question`, or stop.

## Conclusion

The conclusion is the deliverable of exploring — it carries the aligned scope into the next skill. It lives in the conversation (no file); the next skill consumes it and persists what it needs.

### No source of truth here

Exploring produces no artifact and touches no truth. The spec/design remain the source of truth; the Plan (once written) becomes the operative truth during development execution; docs remain truth for documentation.

## Self-review checklist

- [ ] Work type (documentation / development) correctly identified.
- [ ] Scope clear; in/out boundaries stated.
- [ ] Doc changes (if any) stay at requirements level for specs; tech detail in design.
- [ ] Open questions resolved or explicitly flagged.

## Hard constraints

- Touch no file. Exploring produces no artifact; the conclusion lives in the conversation.
- Never skip the HARD-GATE. User review of the conclusion and routing is mandatory.
