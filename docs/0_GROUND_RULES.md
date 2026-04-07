# Ground Rules

## Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| Content | Markdown | — |
| Version control | Git + GitHub | — |

> **The stack above is fixed.** Do not introduce alternatives without explicit approval.

## Inviolable Rules

1. **One concept per file** in `concepts/` — no mega-documents
2. **One source per file** in `readings/` — each book/article/scenario gets its own file
3. **Always cite sources** — link to the original when referencing claims
4. **Date all entries** — ISO 8601 (YYYY-MM-DD)
5. **No duplicated content** — if something belongs in `resources/`, don't repeat it in `readings/`
6. **Template obrigatório** — files in `readings/` and `concepts/` follow the templates in `docs/2_ARCHITECTURE.md`
7. **Atomic changes** — one topic per commit
8. **No unrelated refactoring** — one concern per task
9. **No file renaming or deletion** outside task scope
10. **Repo is the single source of truth** — all knowledge lives here in Markdown

## Content Language

All content in Portuguese (pt-PT), except when quoting English sources.

## File Naming

- Lowercase, hyphens for spaces: `the-alignment-problem.md`
- No numbered prefixes in content folders (`readings/`, `concepts/`, `ideas/`)
- Numbered prefixes only in `docs/` for ordering

## Protected Files (Read-Only)

These files are managed by governance — changes require updating `CHANGELOG.md`:

- `CLAUDE.md`
- `SYSTEM_PROMPT.md`
- `docs/0_GROUND_RULES.md`
- `.gitignore`
