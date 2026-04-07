# Contributing

## Getting Started

### Prerequisites

- Git
- GitHub CLI (`gh`)

### Local Setup

```bash
git clone https://github.com/gtcuco-personal/ai-safety.git
cd ai-safety
```

## Development Workflow

### Branch Strategy

- **Content** (readings, concepts, resources): commit directo em `main`
- **Governance** (docs/, CLAUDE.md, SYSTEM_PROMPT.md): criar branch
- Branch naming: `docs/description`, `content/description`

### Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
docs: add reading notes for human-compatible
content: add interpretability concept note
chore: update roadmap with april progress
```

### Pull Requests

- Keep PRs focused (one concern per PR)
- Include a clear description of what changed and why
- `docs/5_ROADMAP_AND_TASKS.md` — add completed entry with date and description
- `CHANGELOG.md` — add entry for governance changes

## Protected Files

The following files should not be edited without updating `CHANGELOG.md`:

- `CLAUDE.md`
- `SYSTEM_PROMPT.md`
- `docs/0_GROUND_RULES.md`

## Decision Records (ODR)

This project uses Organisational Decision Records to document structural and governance decisions.

### Namespace Convention

| Directory | Purpose | Managed by |
|---|---|---|
| `docs/decisions/` | ODRs created within this repo | Repo maintainer |
| `docs/decisions/template/` | ODRs inherited from the base governance template | Template repo |

- **Local ODRs** use sequential numbering scoped to the repo
- **Template ODRs** keep their original numbering from the template repo
- `docs/decisions/TEMPLATE.md` is the format template for creating new ODRs

## Questions?

Open a GitHub issue or contact the maintainer directly.
