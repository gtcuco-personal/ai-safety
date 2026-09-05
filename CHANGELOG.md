# Changelog

## 2026-09-03 — Redução de execuções do GitHub Actions

- Centralizada a detecção de Node, Deno e fixtures do template num único job; os jobs pesados deixam de arrancar apenas para fazer skip.
- `build-test`, `deno-check`, `template-tests` e `governance-check` passam a correr apenas em pull requests; `gitleaks` mantém cobertura em pull requests e em pushes directos para `main`.

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2.0] — 2026-07-19

### Changed

- Declared the minimal product-and-evidence contract and profile.

## 2026-05-07 — Migração path local: ~/Documents/github → ~/devs/github (#10)

- Repo movido localmente para fora do iCloud Drive (eviction provocava falhas de acesso)
- Path references actualizadas em CLAUDE.md (mergeada em PR #10)

## [1.0] — 2026-04-07

### Added

- Governance structure adapted from `ai-product-architecture-template` v1.13
- `CLAUDE.md` — AI agent entry point with Context Loading Policy
- `SYSTEM_PROMPT.md` — operating instructions adapted for knowledge base repos
- `CONTRIBUTING.md` — workflow, conventions, ODR namespace
- `docs/0_GROUND_RULES.md` — inviolable rules and conventions
- `docs/1_CONTEXT.md` — motivation, objectives, scope
- `docs/2_ARCHITECTURE.md` — directory structure and content templates
- `docs/5_ROADMAP_AND_TASKS.md` — study roadmap and progress tracking
- `docs/decisions/TEMPLATE.md` — ODR format template
- `tasks/lessons.md` — self-improvement loop
- `skills/template/SKILL.md` — agent skill template
- `concepts/alignment.md` — first concept documented
- `readings/ai-2027.md` — first reading notes
- `resources/index.md` — curated links (books, courses, organisations)
- `study-plan/90-days.md` — 90-day study plan
- `ideas/open-questions.md` — open questions and reflections
- `.gitignore` — standard ignores
- `LICENSE` — MIT
