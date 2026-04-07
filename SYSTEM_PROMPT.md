# SYSTEM OPERATING INSTRUCTIONS

> Version: 1.0 — Adapted from ai-product-architecture-template v1.13 for knowledge base repos.

---

## 1. Source of Truth

This project uses modular documentation in `/docs/`. Consult the relevant files before any task. Load only what is needed for the task type — do not load all docs by default. The **Context Loading Policy** in `CLAUDE.md` defines which files to load per task type:

| File | Purpose |
|---|---|
| `docs/0_GROUND_RULES.md` | Conventions, inviolable rules, protected files |
| `docs/1_CONTEXT.md` | Motivation, objectives, scope |
| `docs/2_ARCHITECTURE.md` | Directory structure, templates, conventions |
| `docs/5_ROADMAP_AND_TASKS.md` | Study roadmap, progress tracking, backlog |
| `docs/decisions/` | Local ODRs — decisions made within this repo |
| `docs/decisions/template/` | Template ODRs — inherited from the base governance template |

### Conflict Resolution

- If two docs contradict each other, `0_GROUND_RULES.md` wins.
- If a doc is **missing**: create a skeleton with `TODO` placeholders, flag it to the user.
- If a doc is **outdated** (references removed files, stale data), flag it to the user and propose an update.
- If a doc is **ambiguous** on a point critical to the current task, STOP and ask.

---

## 2. Guardrails

### Content Quality
- All content follows the templates defined in `docs/2_ARCHITECTURE.md`.
- One concept per file in `concepts/`. One source per file in `readings/`.
- Always cite sources — link to the original when referencing claims.
- Date all entries — ISO 8601 (YYYY-MM-DD).
- No duplicated content — if something belongs in `resources/`, don't repeat it in `readings/`.

### Data Formats
- **Dates:** ISO 8601 — `YYYY-MM-DD`
- **Languages:** ISO 639-1 — two-letter codes (`pt`, `en`)
- **Locales:** BCP 47 — language + region (`pt-PT`, `en-GB`)

### File Naming
- Lowercase, hyphens for spaces: `the-alignment-problem.md`
- No numbered prefixes in content folders (`readings/`, `concepts/`, `ideas/`)
- Numbered prefixes only in `docs/` for ordering

---

## 3. Execution Protocol

### Task Types

| Task type | Roadmap update | Branch required |
|---|---|---|
| **Content** (readings, concepts, resources) | Required | No (commit to main) |
| **Governance** (docs, CLAUDE.md, SYSTEM_PROMPT.md) | Required | Yes |
| **Study plan** (progress updates) | If milestone | No |
| **Investigation** (research, analysis) | Skip | No |

### After Every Content Task

1. **Atomic changes** — one concern per task. Do not bundle unrelated changes.
2. **List changed files** — explicitly state every file created, modified, or deleted.
3. **Update the roadmap** — add an entry to `docs/5_ROADMAP_AND_TASKS.md`:
   ```
   - YYYY-MM-DD — Brief description → `file1`, `file2`
   ```

### Uncertainty Criteria

STOP and ask the user when:
- The task requires modifying a **protected file**.
- The task **materially expands scope** beyond the requested change.
- The expected structure is **not documented** in any `/docs/` file.
- The task involves **deleting** content.
- You need to choose between **two valid approaches** with different trade-offs.

---

## 3A. Workflow Orchestration

### Plan Node Default
For any task with 3+ steps or structural decisions: enter plan mode first. Outline steps, identify risks, then execute.

### Subagent Strategy
When a task requires research or exploration separable from the main work: delegate to a subagent. One task per subagent.

### Self-Improvement Loop
After ANY correction from the user, append an entry to `tasks/lessons.md`:
```
### YYYY-MM-DD — [one-line summary]
- **Trigger:** [what went wrong]
- **Lesson:** [what to do differently]
- **Applies to:** [scope]
```

---

## 4. Git Workflow

- Repo pessoal — commit directo em `main` para conteúdo.
- Branch required para governance changes.
- Commit messages follow [Conventional Commits](https://www.conventionalcommits.org/).

---

## 5. Protected Files

Files listed as protected in `docs/0_GROUND_RULES.md` are **read-only** — never edit them directly.

> The definitive list lives in `docs/0_GROUND_RULES.md`. Always check there.

---

## 6. Documentation Standards

This project maintains the following files at the repository root:

| File | Purpose |
|---|---|
| `CLAUDE.md` | AI agent entry point — repo metadata, structure, quick reference |
| `CONTRIBUTING.md` | Workflow, conventions, decision records |
| `CHANGELOG.md` | Version history |

When a task makes a non-obvious structural decision, propose creating a local ODR in `docs/decisions/` using `docs/decisions/TEMPLATE.md`.

### Documentation Maintenance

| Change type | Update required |
|---|---|
| New reading or concept | `docs/5_ROADMAP_AND_TASKS.md` |
| New content template or convention | `docs/2_ARCHITECTURE.md` |
| Scope or objective change | `docs/1_CONTEXT.md` |
| Structural decision (trade-off) | `docs/decisions/` (new local ODR) |
| Governance change | `CHANGELOG.md` |

> **The task is NOT complete until the corresponding docs are updated.**

---

## 7. Execution Modes

| Mode | Detection | Behaviour |
|---|---|---|
| **A — Full access** | Terminal/bash and file write available | Execute tasks end-to-end |
| **B — Workspace only** | File write available, no terminal | Propose changes as code blocks |
| **C — Review only** | Read-only or pasted context only | Analyse and suggest |

---

## 8. Task Completion Checklist

A task is only **done** when all applicable items are confirmed:

- [ ] Changes are within the requested scope — nothing extra
- [ ] Changed files are listed explicitly
- [ ] `docs/5_ROADMAP_AND_TASKS.md` updated (content tasks)
- [ ] Documentation trigger table checked — affected docs updated (§6)
- [ ] No protected files modified
- [ ] User informed of any risks, trade-offs, or follow-up items

---

## Changelog

| Version | Date | Changes |
|---|---|---|
| 1.0 | 2026-04-07 | Initial — adapted from ai-product-architecture-template v1.13 for knowledge base repos |
