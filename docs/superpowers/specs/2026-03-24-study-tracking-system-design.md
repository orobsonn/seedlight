# Seedlight Study Tracking System — Design Spec

*2026-03-24 — v2 (pos-review)*

## Objetivo

Construir um sistema de gestao de conhecimento usando Obsidian + Claude Code skills que acompanhe o estudo do guia de 24 semanas do Seedlight, registre aprendizados e insights, e construa progressivamente uma base de conhecimento aplicado que alimente as decisoes de design e implementacao do projeto.

O vault nao e um repositorio academico. E a base de conhecimento aplicado que vai alimentar o Seedlight quando formos construi-lo.

## Decisoes de Design

### Vault dedicado

Vault Obsidian separado (nao integrado a vault pessoal existente). Mantido dentro do repositorio Seedlight em `seedlight-vault/`. A pasta `.obsidian/` deve ser parcialmente gitignored (workspace.json e cache sim, plugins e settings opcionalmente trackados para reproducibilidade).

### Fonte unica de verdade

Tudo vive no vault — progresso, conhecimento, decisoes de design. Nao ha dependencia do Claude Code para tracking de estado. O Claude le o vault no inicio de cada sessao para se atualizar.

### Grafo organico

Links bidirecionais emergem organicamente durante o estudo, sem estrutura forcada. O graph view do Obsidian reflete as conexoes reais entre conceitos, nao uma taxonomia imposta.

### GraphRAG

A implementacao especifica do GraphRAG (storage, algoritmos, integracao) sera definida durante a Fase 3 do guia de estudos (Areas 3.3 e 4.3). A spec do vault nao prescreve a solucao tecnica — o estudo vai informar essa decisao.

---

## Estrutura do Vault

```
seedlight-vault/
├── .gitignore                # ignora .obsidian/workspace.json e cache
├── dashboard.md              # indice vivo de progresso (atualizado incrementalmente)
├── sources/
│   ├── papers/
│   ├── repos/
│   └── books/
├── concepts/
├── design/
├── journal/
└── templates/
    ├── source-paper.md
    ├── source-repo.md
    ├── concept.md
    ├── design.md
    └── journal-entry.md
```

### Tres niveis de notas

**Sources** — ficha do paper/repo/livro com metadados e resumo pratico. Ponto de entrada, nao destino. Valor esta nos conceitos extraidos.

**Concepts** — nota atomica sobre um conceito. Uma ideia = uma nota. Cada nota tem campo `kind` que classifica o tipo de conhecimento e `seedlight-component` que indica qual componente do Seedlight e impactado.

**Design** — decisao ou hipotese de design para o Seedlight, derivada dos conceitos. Ponte entre ciencia e engenharia. Linka para os conceitos que a fundamentam.

O `journal/` registra sessoes de estudo. O `dashboard.md` e o indice vivo de progresso, atualizado incrementalmente por `/review` e `/insight`.

### Convencoes de nomes de arquivo

- **Kebab-case, lowercase, sem acentos**
- Sources (papers): `autor-ano-titulo-curto.md` — ex: `kapur-2008-productive-failure.md`
- Sources (repos): `nome-do-repo.md` — ex: `nano-graphrag.md`
- Concepts: `nome-do-conceito.md` — ex: `productive-failure.md`, `triple-storage-pattern.md`
- Design: `componente-decisao.md` — ex: `companion-operar-na-zpd.md`
- Journal: `YYYY-MM-DD.md` — ex: `2026-03-24.md` (uma entry por dia, sessoes do mesmo dia se acumulam)

---

## Frontmatter

### Vocabulario unificado de componentes

Um unico vocabulario para `seedlight-component`, usado tanto em Concepts quanto em Design:

```
companion | curriculum | bkt | graphrag | context-adapter | engagement | equity-layer | orchestrator | ui | infra | all
```

Onde:
- `companion` — o agente longitudinal (LLM + memoria + personalidade)
- `curriculum` — grafo curricular, conteudo, sequenciamento
- `bkt` — knowledge tracing (Bayesian e variantes)
- `graphrag` — motor de retrieval baseado em grafos
- `context-adapter` — adaptacao de conceitos ao contexto da crianca
- `engagement` — deteccao de estado de engajamento
- `equity-layer` — camada de equidade preditiva
- `orchestrator` — coordenacao dos componentes
- `ui` — interface da crianca
- `infra` — infraestrutura (SQLite, llama.cpp, sync, deploy)
- `all` — transversal a todos os componentes

### Source (paper/book/repo)

```yaml
---
type: paper | book | repo | blog | talk
areas: ["1.1"]
status: to-read | reading | done
date: 2026-03-24
authors: []
year:
tags: []
---
```

### Concept

```yaml
---
kind: principle | framework | metric | pattern | antipattern | sequence | technique | constraint | case-study | lesson
sources: ["[[Nome da Source]]"]
seedlight-component: companion | curriculum | bkt | graphrag | context-adapter | engagement | equity-layer | orchestrator | ui | infra | all
tags: []
---
```

### Design

```yaml
---
seedlight-component: companion | curriculum | bkt | graphrag | context-adapter | engagement | equity-layer | orchestrator | ui | infra | all
status: hypothesis | validated | implemented
based-on: []
tags: []
---
```

O status `implemented` significa que existe codigo correspondente no repositorio Seedlight que materializa esta decisao de design.

### Journal Entry

```yaml
---
date: 2026-03-24
areas: ["1.1", "6.2"]
sources-studied: []
tags: []
---
```

---

## Taxonomia de Conhecimento (10 kinds)

| kind | Descricao | Exemplo |
|------|-----------|---------|
| `principle` | Principio filosofico ou de design | "Conhecimento e construido, nao transmitido" (Papert) |
| `framework` | Modelo multi-dimensional, taxonomia | SDT (autonomia, competencia, vinculo) |
| `metric` | Definicao formal, formula, medicao | Equalized odds, 2 Sigma de Bloom |
| `pattern` | Padrao arquitetural, de codigo, de dados | Triple-storage, schema (aluno, conceito, acertou?) |
| `antipattern` | Red flag nomeada, coisa a evitar | Portability Trap, soft bigotry of low expectations |
| `sequence` | Processo ordenado, pipeline, fases | Productive Failure (exploracao -> consolidacao) |
| `technique` | Metodo de implementacao, configuracao | Quantizacao Q4_K_M, DP-SGD, Betweenness Centrality |
| `constraint` | Restricao formal, impossibilidade | Impossibilidade de Friedler, orcamento de privacidade |
| `case-study` | Exemplo narrativo, deployment real | Kolibri em campos de refugiados |
| `lesson` | Insight operacional, correcao, descoberta | sqlite-vss deprecated, MiniRAG existe |

---

## Vocabulario de Tags (fechado)

### Temas transversais

- `#offline-first` — funcionamento sem internet
- `#on-device` — execucao no dispositivo da crianca
- `#privacy` — privacidade e soberania de dados
- `#fairness` — equidade e justica
- `#longitudinal` — acompanhamento ao longo de anos
- `#scaffolding` — tecnicas de andaimento pedagogico
- `#motivation` — motivacao e engajamento
- `#assessment` — avaliacao de aprendizagem

### Prioridade

- `#critical` — sem isso o Seedlight nao funciona
- `#foundational` — base conceitual que informa tudo
- `#future` — relevante mas nao para o MVP

### Estado epistemico

- `#validated` — confirmado por multiplas fontes ou teste pratico
- `#tension` — conflito ou trade-off nao resolvido
- `#open-question` — duvida que precisa investigacao

### Regras

1. Maximo 3-4 tags por nota
2. Nao criar tags novas sem discutir primeiro — proposta de tag nova deve ser registrada como nota de design com justificativa
3. Tags nao substituem links

---

## Estrategia de Conexoes

### Regra de ouro

**Nunca criar link sem frase que explique POR QUE o link existe.**

Links sempre aparecem dentro de prosa contextualizada, nunca em listas soltas. O contexto da frase e o tipo semantico do link.

### Tres padroes de conexao

**Source -> Concept (extracao):** Na source, secao "Conceitos Extraidos" com frase curta. No concept, campo `sources` no frontmatter.

**Concept <-> Concept (relacao organica):** Dentro das secoes "O que e" ou "Por que importa para o Seedlight". A prosa ao redor do link expressa a natureza da relacao (alinhamento, tensao, dependencia, complemento).

**Concept -> Design (implicacao):** No concept, secao "Por que importa para o Seedlight" linka para notas de design. Na design note, secao "Fundamentacao" linka de volta para concepts.

### Resultado no graph view

Clusters naturais emergem:
- Cluster pedagogico (ZPD, Productive Failure, Mastery Learning, SDT)
- Cluster de fairness (Friedler, Portability Trap, Aequitas)
- Cluster de infra (triple-storage, sqlite-vec, llama.cpp, quantizacao)

Notas de `design/` sao nos-ponte entre clusters.

---

## Skills do Claude Code

### Ciclo de vida de uma sessao de estudo

```
/study → (estudo + /insight durante) → /review → sessao encerrada
```

- Uma sessao comeca com `/study` e termina com `/review`
- `/insight` pode ser usado quantas vezes quiser durante a sessao
- `/review` deve ser chamado antes de iniciar um novo `/study`
- Se `/study` for chamado sem `/review` anterior, o Claude alerta e propoe rodar o review primeiro
- Uma sessao por dia no journal (se houver multiplas, acumulam na mesma entry)

### /study — Inicio de sessao de estudo

1. Le `dashboard.md` para saber progresso atual
2. Le entry mais recente de `journal/` para contexto
3. Pergunta o que estudar hoje
4. Cria nota de Source se for material novo
5. Entra em modo de estudo conjunto: leitura, discussao, questionamento
6. Propoe registro de conceitos conforme surgem
7. Cria links organicamente durante a conversa

### /insight — Registro de insight

1. Recebe insight (texto livre ou proposto pelo Claude)
2. Classifica `kind` e `seedlight-component`
3. Busca notas existentes que podem se conectar
4. Cria nota em `concepts/` ou `design/` com links contextualizados
5. Atualiza notas relacionadas com backlinks
6. Atualiza `dashboard.md` incrementalmente (contadores)

### /review — Revisao de fim de sessao

1. Rele toda a conversa
2. Extrai insights nao registrados
3. Propoe cada um para aprovacao
4. Cria entry em `journal/` com: data, material estudado, insights, duvidas, proximos passos
5. Atualiza `dashboard.md` incrementalmente

### /progress — Dashboard de progresso

Le `dashboard.md` (que e mantido atualizado incrementalmente por `/review` e `/insight`). Se o usuario pedir recalculo completo, faz scan de todas as notas e reconstroi o dashboard do zero.

### /synthesize (futuro)

Analise cruzada do vault inteiro. Identifica conceitos isolados, propoe conexoes, gera hipoteses de design. Ativar quando o vault tiver multiplos clusters de conceitos com pelo menos 3 nos cada.

### Hook: lembrete de review

Ao final de conversas longas, lembrar de rodar `/review` se nao foi feito.

---

## Templates

### source-paper.md

```markdown
---
type: paper
areas: []
status: to-read
date: {{date}}
authors: []
year:
tags: []
---

# {{title}}

## Resumo Pratico

## Conceitos Extraidos

## Citacoes-Chave

## Duvidas Abertas
```

### source-repo.md

```markdown
---
type: repo
areas: []
status: to-read
date: {{date}}
url: ""
tags: []
---

# {{title}}

## O que faz

## Padroes Arquiteturais

## O que estudar no codigo

## Relevancia para o Seedlight
```

### concept.md

```markdown
---
kind:
sources: []
seedlight-component:
tags: []
---

# {{title}}

## O que e

## Por que importa para o Seedlight
```

### design.md

```markdown
---
seedlight-component:
status: hypothesis
based-on: []
tags: []
---

# {{title}}

## Decisao / Hipotese

## Fundamentacao

## Trade-offs

## Status
```

### journal-entry.md

```markdown
---
date: {{date}}
areas: []
sources-studied: []
tags: []
---

# Sessao {{date}}

## O que estudei

## Insights registrados

## Duvidas abertas

## Proximos passos
```

---

## CLAUDE.md

O arquivo `CLAUDE.md` na raiz do repositorio contem instrucoes persistentes para o Claude Code. Inclui: visao do projeto, papel do Claude (mentor desafiador), estrutura do vault, convencoes de frontmatter/tags/links, skills disponiveis, decisoes tecnicas relevantes, e vocabulario unificado de componentes.

Conteudo completo no arquivo `CLAUDE.md` na raiz do repositorio.

---

## Descobertas da Pesquisa

Durante a pesquisa para este design, foram identificadas informacoes que devem ser incorporadas ao guia de estudos:

1. **sqlite-vss esta deprecated** — o sucessor e sqlite-vec (C puro, zero dependencias, roda em RPi Zero)
2. **MiniRAG** (HKUDS/MiniRAG) — do mesmo time do LightRAG, desenhado especificamente para SLMs de 1.5B. Usa apenas 25% do storage de RAG tradicional. Candidato forte para o Seedlight
3. **GRPO** e o algoritmo RL ideal — nao precisa de value model separado, economiza ~30-40% de memoria vs PPO
4. **Mem0 com Ollama** — blueprint pratico para memoria on-device (Ollama + nomic-embed-text + SQLite)
5. **Aequitas** — formaliza que em educacao (intervencao assistiva) o erro critico e o falso negativo

---

## Implementacao

1. Criar vault Obsidian com estrutura de pastas, .gitignore, e templates
2. Popular dashboard.md com estrutura do guia de estudos
3. Criar as 4 skills do Claude Code (/study, /insight, /review, /progress)
4. Configurar hook de lembrete de review
5. Atualizar guia de estudos com descobertas da pesquisa (sqlite-vss -> sqlite-vec, adicionar MiniRAG, adicionar GRPO/veRL)
6. Atualizar CLAUDE.md com vocabulario unificado de componentes
