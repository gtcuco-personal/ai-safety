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
| Agent safety review | `docs/10_AGENT_SAFETY.md`, `SYSTEM_PROMPT.md` | All others |

> Always load `docs/0_GROUND_RULES.md` for any content task — it is the override document.
> Always load `tasks/lessons.md` at session start for any task type — it contains repo-specific corrections.

## Agent Skills

Este repo inclui um directório `skills/` com templates para criar Agent Skills específicas ao projecto. Skills globais (usadas em múltiplos repos) vivem em `~/.claude/skills/`.

Ver `docs/9_AGENT_SKILLS.md` para o guia completo (framework KEPT, estrutura, regras) — quando existir.

## Cross-Reference Index

If this repo contains an `INDEX.md` (common in academic/study repos), always read it before answering questions about the content it maps. The INDEX.md provides cross-references between topics, sources, and materials that are not obvious from the directory structure alone.

## Related Projects

| Project | Relationship |
|---------|-------------|
| `ai-product-architecture-template` | Template de governance base |
