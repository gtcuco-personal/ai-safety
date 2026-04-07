# Architecture

## Estrutura de directórios

```
ai-safety/
├── concepts/        # Um ficheiro por conceito de AI safety
├── readings/        # Um ficheiro por fonte (livro, artigo, cenário, paper, palestra)
├── resources/       # Links curados (cursos, organizações, pessoas)
├── study-plan/      # Planos de estudo e progresso
├── ideas/           # Perguntas abertas e reflexões
└── docs/            # Meta-documentação sobre o repo
```

## Propósito de cada directório

| Directório | Contém | Convenção de nomes |
|------------|--------|-------------------|
| `concepts/` | Um ficheiro por conceito de AI safety | `nome-do-conceito.md` |
| `readings/` | Um ficheiro por fonte lida/anotada | `nome-da-fonte.md` |
| `resources/` | Colecções curadas de links | `index.md` + ficheiros por tópico |
| `study-plan/` | Planos de aprendizagem e tracking | nome descritivo |
| `ideas/` | Perguntas abertas e reflexões | nome descritivo |
| `docs/` | Meta-documentação | prefixo numérico |

## Template — Notas de leitura (`readings/`)

```markdown
# [Título] — Notas de leitura

**Fonte:** [URL ou referência]
**Autor(es):** [nomes]
**Tipo:** Livro | Artigo | Cenário | Paper | Palestra
**Lido:** [YYYY-MM]

---

## O que é
[1-2 frases]

## Argumento central
[tese principal]

## Mecanismos-chave
[conceitos principais, em lista]

## Citações importantes
[citações relevantes]

## Perguntas em aberto
[questões levantadas]

## Ligação a outras leituras
[referências cruzadas a outros ficheiros em readings/ ou concepts/]
```

## Template — Nota de conceito (`concepts/`)

```markdown
# [Nome do conceito]

## Definição
[definição clara]

## Porque importa
[relevância para AI safety]

## Fontes
[links para ficheiros em readings/ e fontes externas]

## Estado do conhecimento
[o que está estabelecido vs. em debate]
```
