# AI Safety — Knowledge Base

Base de conhecimento pessoal sobre AI safety, alignment, e governance.

## Repository

| Key | Value |
|-----|-------|
| **Local path** | `~/Documents/github/ai-safety` |
| **Remote** | `https://github.com/gtcuco-personal/ai-safety.git` |
| **GitHub account** | `gtcuco-personal` |
| **Production URL** | N/A |

## Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| Content | Markdown | — |
| Version control | Git + GitHub | — |

## Commands

```bash
# Knowledge base — no build commands
git status
git log --oneline -10
```

## Project Structure

```
ai-safety/
├── CLAUDE.md                       # AI agent entry point
├── SYSTEM_PROMPT.md                # AI agent operating instructions
├── CONTRIBUTING.md                 # Workflow e convenções
├── CHANGELOG.md                    # Versão e histórico
├── README.md                       # Descrição pública
├── docs/
│   ├── 0_GROUND_RULES.md          # Convenções e regras invioláveis
│   ├── 1_CONTEXT.md               # Motivação, objectivos, âmbito
│   ├── 2_ARCHITECTURE.md          # Estrutura de directórios, templates
│   ├── 5_ROADMAP_AND_TASKS.md     # Roadmap de estudo e progresso
│   └── decisions/
│       ├── TEMPLATE.md            # Formato ODR
│       └── template/              # ODRs herdados do template base
├── concepts/                       # Um ficheiro por conceito de AI safety
├── readings/                       # Um ficheiro por fonte (livro, artigo, cenário)
├── resources/                      # Links curados (cursos, organizações, pessoas)
├── study-plan/                     # Planos de estudo
├── ideas/                          # Perguntas abertas e reflexões
├── tasks/                          # Task tracking e lessons learned
│   └── lessons.md
└── skills/                         # Agent Skills específicas ao repo
    └── template/
        └── SKILL.md
```

## Key Patterns

- **Um ficheiro por conceito** em `concepts/` — sem mega-documentos
- **Um ficheiro por fonte** em `readings/` — templates em `docs/2_ARCHITECTURE.md`
- **Repo é a single source of truth** — todo o conhecimento vive aqui em Markdown

## Git Workflow

> Repo pessoal de conhecimento — commit directo em `main` é aceitável para conteúdo.
> Para alterações à governance (docs/, CLAUDE.md, SYSTEM_PROMPT.md): criar branch.

1. Branch naming: `docs/description`, `content/description`
2. Commit messages: Conventional Commits
3. Push: `git push -u origin docs/description`

## Context Loading Policy

Before starting any task, load only the files relevant to that task type. Do not load all `/docs/` files by default.

| Task type | Load | Skip |
|---|---|---|
| Adicionar notas de leitura | `docs/0_GROUND_RULES.md`, `docs/2_ARCHITECTURE.md` | `docs/1_CONTEXT.md` |
| Adicionar conceito | `docs/0_GROUND_RULES.md`, `docs/2_ARCHITECTURE.md` | `docs/1_CONTEXT.md` |
| Actualizar plano de estudo | `docs/0_GROUND_RULES.md`, `docs/5_ROADMAP_AND_TASKS.md` | `docs/2_ARCHITECTURE.md` |
| Adicionar recurso | `docs/0_GROUND_RULES.md`, `docs/2_ARCHITECTURE.md` | `docs/1_CONTEXT.md` |
| Planeamento / reflexão | `docs/1_CONTEXT.md`, `docs/5_ROADMAP_AND_TASKS.md` | `docs/2_ARCHITECTURE.md` |
| Governance change | `docs/0_GROUND_RULES.md`, `SYSTEM_PROMPT.md` | All others |
| Agent skill — create/edit | `docs/9_AGENT_SKILLS.md`, `skills/template/SKILL.md` | All others |
| Agent safety review | `docs/10_AGENT_SAFETY.md`, `SYSTEM_PROMPT.md` | All others |

| Code — content layer decision (i18n vs storage vs MD) | `docs/0_GROUND_RULES.md`, `docs/7_CONTENT_I18N.md`, `docs/2_ARCHITECTURE.md` | `docs/3_UI_UX_GUIDELINES.md`, `docs/6_CONTENT_AND_SOCIAL.md` |
> Always load `docs/0_GROUND_RULES.md` for any content task — it is the override document.
> Always load `tasks/lessons.md` at session start for any task type — it contains repo-specific corrections.

## Agent Skills

Este repo inclui um directório `skills/` com templates para criar Agent Skills específicas ao projecto. Skills globais (usadas em múltiplos repos) vivem em `~/.claude/skills/`.

Ver `docs/9_AGENT_SKILLS.md` para o guia completo (framework KEPT, estrutura, regras) — quando existir.


## Isolated Work (worktree subagents)

Este repo inclui subagents pré-configurados em `.claude/agents/` para trabalho que não deve tocar directamente no working directory principal.

| Subagent | Isolamento | Quando delegar |
|---|---|---|
| `isolated-worker` | `worktree` (git worktree temporário) | Refactors >3 ficheiros, migrações de schema, upgrades de dependências, experiências arriscadas |
| `safe-explorer` | read-only (sem Write/Edit/Bash) | Perguntas de exploração, "onde está X", "como funciona Y", investigações de arquitectura |

**Como invocar (a partir da sessão principal):**

```
Agent({
  subagent_type: "isolated-worker",
  isolation: "worktree",
  description: "Refactor auth middleware",
  prompt: "<detailed task brief>"
})
```

**Limitação conhecida:** A sessão principal do Claude Code edita sempre directamente no working directory — o isolamento por worktree só se aplica a subagents spawnados via `Agent` tool. Para trabalho directo na sessão principal, manter a regra *"nunca push directo para `main`"* (ver Git Workflow acima).

**Quando NÃO usar isolated-worker:** edits simples (<3 ficheiros), bug fixes pontuais, alterações de copy/content. O overhead de criar worktree não compensa.

## Context7 — Documentação de Bibliotecas

Para qualquer biblioteca, framework, SDK, API ou CLI listada no **Tech Stack** acima, usar **Context7** antes de responder sobre ela — evita sintaxe desactualizada e garante que as respostas reflectem a versão em uso.

| Quando usar | Como usar |
|---|---|
| Pergunta sobre API/sintaxe de uma lib | `mcp__context7__resolve-library-id` → `mcp__context7__query-docs` |
| Review de arquitectura (`/arch-review`) | Context7 para cada tecnologia do stack |
| Debugging de lib específica | Context7 com tópico relevante (ex: `authentication`, `rls`, `hooks`) |
| Migração de versão | Context7 com tópico `migration` ou `changelog` |

> Não usar Context7 para: lógica de negócio, refactoring, code review, conceitos gerais de programação.

## Cross-Reference Index

If this repo contains an `INDEX.md` (common in academic/study repos), always read it before answering questions about the content it maps. The INDEX.md provides cross-references between topics, sources, and materials that are not obvious from the directory structure alone.

## Related Projects

| Project | Relationship |
|---------|-------------|
| `ai-product-architecture-template` | Template de governance base |

## INDEX.md — mandatory governance file

**Every repo governed by this template must have an `INDEX.md` at the root.** It is a live map of active initiatives, folder purpose, and archived work. Treat it with the same priority as `CHANGELOG.md` and `docs/5_ROADMAP_AND_TASKS.md`.

### How agents must use it

1. **Always read `INDEX.md` first** when entering a repo, before exploring with `find`/`grep`. It saves tokens and gives the canonical map.
2. **If `INDEX.md` has `[preencher]` placeholders** (never populated), offer to auto-populate it from the roadmap, stakeholder folder, and folder structure — before continuing with the user's task.
3. **If `INDEX.md` is stale** (date > 30 days or missing recent initiatives visible in roadmap/commits), flag it and offer to refresh.

### Maintenance obligations

- `/sync-repos` audits presence and auto-populates on first creation
- `/sync-docs` refreshes the INDEX on every sync (active initiatives from roadmap, archive from completed items, updates "Last updated")
- Every PR that adds, moves, or removes artifacts in `stakeholders/`, `pitches/`, `research/`, `decisions/`, `meetings/` (or equivalent) must update `INDEX.md` — same rule as CHANGELOG and roadmap

See `INDEX.md` template for the required structure.

