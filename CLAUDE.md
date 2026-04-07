# AI Safety — Knowledge Base

Base de conhecimento pessoal sobre AI safety, alignment, e governance.

## Repository

| Key | Value |
|-----|-------|
| **Local path** | `~/Documents/github/ai-safety` |
| **Remote** | `gtcuco-personal/ai-safety` |
| **Type** | Knowledge base / study repo |
| **Language** | Português (pt-PT), citações em inglês |

## Project Structure

```
ai-safety/
├── CLAUDE.md                       # AI agent entry point
├── CHANGELOG.md                    # Versão e histórico
├── README.md                       # Descrição pública
├── docs/
│   ├── 0_GROUND_RULES.md          # Convenções e regras
│   ├── 1_CONTEXT.md               # Motivação e objectivos
│   ├── 2_ARCHITECTURE.md          # Estrutura, templates, convenções
│   └── 5_ROADMAP_AND_TASKS.md     # Roadmap de estudo e progresso
├── concepts/                       # Um ficheiro por conceito de AI safety
├── readings/                       # Um ficheiro por fonte (livro, artigo, cenário)
├── resources/                      # Links curados (cursos, organizações, pessoas)
│   └── index.md
├── study-plan/                     # Planos de estudo
│   └── 90-days.md
└── ideas/                          # Perguntas abertas e reflexões
    └── open-questions.md
```

## Context Loading Policy

| Tipo de tarefa | Carregar | Saltar |
|---|---|---|
| Adicionar notas de leitura | `docs/0_GROUND_RULES.md`, `docs/2_ARCHITECTURE.md` | `docs/1_CONTEXT.md` |
| Actualizar plano de estudo | `docs/0_GROUND_RULES.md`, `docs/5_ROADMAP_AND_TASKS.md` | `docs/2_ARCHITECTURE.md` |
| Adicionar recurso | `docs/0_GROUND_RULES.md`, `docs/2_ARCHITECTURE.md` | `docs/1_CONTEXT.md` |
| Planeamento / reflexão | `docs/1_CONTEXT.md`, `docs/5_ROADMAP_AND_TASKS.md` | `docs/2_ARCHITECTURE.md` |

> Carregar sempre `docs/0_GROUND_RULES.md` para qualquer tarefa de conteúdo.

## Git Workflow

- Repo pessoal de conhecimento — commit directo em `main` é aceitável
- Commits atómicos: um tópico por commit

## Related Projects

| Projecto | Relação |
|----------|---------|
| `ai-product-architecture-template` | Template de governance base |
