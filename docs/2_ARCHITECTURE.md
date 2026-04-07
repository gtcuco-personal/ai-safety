# Architecture

## Directory Structure

```
ai-safety/
├── concepts/        # One file per AI safety concept
├── readings/        # One file per source (book, article, scenario, paper, talk)
├── resources/       # Curated link collections
├── study-plan/      # Learning paths and progress
├── ideas/           # Open questions and reflections
├── docs/            # Meta-documentation (governance)
├── tasks/           # Task tracking and lessons learned
└── skills/          # Agent Skills specific to this repo
```

## Directory Purpose

| Directory | Contains | Naming convention |
|-----------|----------|-------------------|
| `concepts/` | One file per AI safety concept | `concept-name.md` |
| `readings/` | One file per source read/annotated | `source-name.md` |
| `resources/` | Curated link collections | `index.md` + topic files as needed |
| `study-plan/` | Learning paths and tracking | descriptive name |
| `ideas/` | Open questions and reflections | descriptive name |
| `docs/` | Meta-documentation | numbered prefix |
| `tasks/` | Lessons learned, corrections | `lessons.md` |
| `skills/` | Agent Skills | `skill-name/SKILL.md` |

## Reading Notes Template

Every file in `readings/` must follow this structure:

```markdown
# [Title] — Notas de leitura

**Fonte:** [URL or reference]
**Autor(es):** [names]
**Tipo:** Livro | Artigo | Cenário | Paper | Palestra
**Lido:** [YYYY-MM]

---

## O que é
[1-2 sentences]

## Argumento central
[key thesis]

## Mecanismos-chave
[main concepts, bulleted]

## Citações importantes
[notable quotes]

## Perguntas em aberto
[questions raised]

## Ligação a outras leituras
[cross-references to other files in readings/ or concepts/]
```

## Concept Note Template

Every file in `concepts/` must follow this structure:

```markdown
# [Concept Name]

## Definição
[clear definition]

## Porque importa
[relevance for AI safety]

## Fontes
[links to readings/ files and external sources]

## Estado do conhecimento
[what's established vs debated]
```

## Data Flow

```
Source (book, article, scenario)
  → readings/ (structured notes)
  → concepts/ (extracted concepts)
  → ideas/ (open questions)
  → resources/ (curated links)
```
