---
name: ww-brainstorming
description: Divergent research — surface alternatives and converge on a decision.
---

# Brainstorming

Diverge across alternatives, then converge on a decision — helping the user complete key details one question at a time. Produces a decision conclusion (chosen alternative + rationale); no file artifact.

## When to use me

Use when the user's direction is genuinely undecided and deserves open exploration: architecture/future decisions, "should we adopt X", "which approach for Y". Invoke when the goal is to weigh alternatives and reach a decision, not to refine a known idea, diagnose a defect, or write a Plan. Do NOT use to converge a rough idea into scope (use `ww-exploring`), diagnose a bug/perf issue (use `ww-analyzing`), write a Plan (use `ww-planning`), or write docs directly (use `ww-writing-doc`). Skip this skill entirely when the decision is already clear.

## Workflow

```mermaid
flowchart TD
    A[1. Explore project] --> B[2. Restate + determine work-type]
    B --> C{Aligned?}
    C -- No --> D[3. Diverge: surface alternatives]
    D --> E[4. Clarify one question at a time]
    E --> F{Converged?}
    F -- No --> D
    F -- Yes --> G[5. Produce decision + routing]
    G --> H[6. Self-review]
    H --> I{Skip?}
    I -- No --> J[Review & fix]
    I -- Yes --> K[7. User review]
    J --> K
    K --> L{Approved?}
    L -- changes --> G
    L -- approved --> M[8. Hand off or stop]
    M --> N{Route}
    N -- documentation --> O[Load ww-writing-doc]
    N -- development --> P[Load ww-planning]
    N -- stop --> Q([Stop])
```

Follow these steps in order.

### 1. Explore the project

Read `AGENTS.md` (foregrounds `docs/constitution.md` and points to `docs/README.md`) → `docs/README.md`, then the relevant docs (`constitution.md`, `architecture.md`, `conventions.md`, `glossary.md`, `specs/`, `design/`, `contracts/`, `adr/`, and `references/` as context) and code. Build a picture of what the project is and how the user's intent fits.

### 2. Restate and determine work-type

Restate the situation to the user and determine the work type for routing: **documentation** (decision lands as an ADR / global design) or **development** (the decision will be implemented). The research mode is brainstorming (you are in it); only the work-type is open.

### 3. Diverge — surface alternatives

Offer multiple, genuinely distinct alternatives for the decision at hand. Don't anchor on the first option. Make the trade-offs between them visible.

### 4. Clarify one question at a time

Use the `question` tool to help the user complete key details, ONE question at a time — let each answer shape the next.

### 5. Produce decision and routing

Converge on a decision: the chosen alternative + rationale, plus intended doc changes (global design / ADR) if any. Route:

- **documentation** → `ww-writing-doc`.
- **development** → `ww-planning` — ONLY when the conclusion contains a chosen alternative. If still divergent, do not route to planning; loop back to step 3 or stop.

### 6. Self-review

Ask via `question` whether to skip self-review (`yes` / `no`). If `no`, check against the [Self-review checklist](#self-review-checklist), fix in place, then summarize.

### 7. User review — HARD-GATE

Present the decision and routing for user review. You MUST NOT proceed until the user explicitly approves. On requested changes, update and re-present. Loop until approval.

### 8. Hand off or stop

On approval, hand off to the routed skill (`ww-writing-doc` or `ww-planning`) via `question`, or stop.

## Conclusion

The conclusion is the deliverable of brainstorming — it carries the decision into the next skill. It lives in the conversation (no file); the next skill consumes it and persists what it needs.

### No source of truth here

Brainstorming produces no artifact and touches no truth. The spec/design remain the source of truth; the Plan (once written) becomes the operative truth during development execution; docs remain truth for documentation.

## Self-review checklist

- [ ] Work type (documentation / development) correctly identified.
- [ ] Multiple distinct alternatives surfaced; trade-offs visible.
- [ ] Decision states the chosen alternative + rationale.
- [ ] If routing to `ww-planning`, the conclusion contains a chosen alternative (not still divergent).
- [ ] Open questions resolved or explicitly flagged.

## Hard constraints

- Touch no file. Brainstorming produces no artifact; the conclusion lives in the conversation.
- Never route to `ww-planning` with a still-divergent conclusion.
- Never skip the HARD-GATE. User review of the decision and routing is mandatory.
