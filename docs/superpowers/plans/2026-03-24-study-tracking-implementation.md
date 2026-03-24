# Study Tracking System — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create the Obsidian vault, Claude Code skills, and dashboard that enable structured study sessions for the Seedlight project.

**Architecture:** An Obsidian vault at `seedlight-vault/` with templates, a dashboard, and 4 Claude Code skills at `.claude/skills/` that read/write the vault. No code dependencies — just markdown files and skill definitions.

**Tech Stack:** Obsidian (markdown vault), Claude Code skills (SKILL.md format), git

**Spec:** `docs/superpowers/specs/2026-03-24-study-tracking-system-design.md`

---

## File Map

```
seedlight/
├── .claude/
│   └── skills/
│       ├── study/
│       │   └── SKILL.md
│       ├── insight/
│       │   └── SKILL.md
│       ├── review/
│       │   └── SKILL.md
│       └── progress/
│           └── SKILL.md
├── seedlight-vault/
│   ├── .gitignore
│   ├── dashboard.md
│   ├── sources/
│   │   ├── papers/.gitkeep
│   │   ├── repos/.gitkeep
│   │   └── books/.gitkeep
│   ├── concepts/.gitkeep
│   ├── design/.gitkeep
│   ├── journal/.gitkeep
│   └── templates/
│       ├── source-paper.md
│       ├── source-repo.md
│       ├── concept.md
│       ├── design.md
│       └── journal-entry.md
└── CLAUDE.md (already exists — no changes needed)
```

---

### Task 1: Create Vault Structure

**Files:**
- Create: `seedlight-vault/.gitignore`
- Create: `seedlight-vault/sources/papers/.gitkeep`
- Create: `seedlight-vault/sources/repos/.gitkeep`
- Create: `seedlight-vault/sources/books/.gitkeep`
- Create: `seedlight-vault/concepts/.gitkeep`
- Create: `seedlight-vault/design/.gitkeep`
- Create: `seedlight-vault/journal/.gitkeep`

- [ ] **Step 1: Create vault directories with .gitkeep files**

```bash
cd /Users/robson/Desktop/dev/seedlight
mkdir -p seedlight-vault/sources/papers
mkdir -p seedlight-vault/sources/repos
mkdir -p seedlight-vault/sources/books
mkdir -p seedlight-vault/concepts
mkdir -p seedlight-vault/design
mkdir -p seedlight-vault/journal
mkdir -p seedlight-vault/templates
touch seedlight-vault/sources/papers/.gitkeep
touch seedlight-vault/sources/repos/.gitkeep
touch seedlight-vault/sources/books/.gitkeep
touch seedlight-vault/concepts/.gitkeep
touch seedlight-vault/design/.gitkeep
touch seedlight-vault/journal/.gitkeep
```

- [ ] **Step 2: Create .gitignore for Obsidian cache**

Create `seedlight-vault/.gitignore`:
```
# Obsidian workspace and cache (user-specific)
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/cache
.trash/
```

- [ ] **Step 3: Verify structure**

```bash
find seedlight-vault -type f | sort
```

Expected: .gitignore, .gitkeep files in each subdirectory.

- [ ] **Step 4: Commit**

```bash
git add seedlight-vault/
git commit -m "feat: create Obsidian vault structure for study tracking"
```

---

### Task 2: Create Templates

**Files:**
- Create: `seedlight-vault/templates/source-paper.md`
- Create: `seedlight-vault/templates/source-repo.md`
- Create: `seedlight-vault/templates/concept.md`
- Create: `seedlight-vault/templates/design.md`
- Create: `seedlight-vault/templates/journal-entry.md`

- [ ] **Step 1: Create source-paper template**

Create `seedlight-vault/templates/source-paper.md`:
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

- [ ] **Step 2: Create source-repo template**

Create `seedlight-vault/templates/source-repo.md`:
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

- [ ] **Step 3: Create concept template**

Create `seedlight-vault/templates/concept.md`:
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

- [ ] **Step 4: Create design template**

Create `seedlight-vault/templates/design.md`:
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

- [ ] **Step 5: Create journal-entry template**

Create `seedlight-vault/templates/journal-entry.md`:
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

- [ ] **Step 6: Commit**

```bash
git add seedlight-vault/templates/
git commit -m "feat: add Obsidian templates for sources, concepts, design, and journal"
```

---

### Task 3: Create Dashboard

**Files:**
- Create: `seedlight-vault/dashboard.md`

The dashboard maps all 12 areas and 6 phases from the study guide, with space for incremental updates by /review and /insight.

- [ ] **Step 1: Create dashboard.md**

Create `seedlight-vault/dashboard.md` with the complete study guide structure mapped to tracking format. Include:
- Header with last-updated date
- Phase overview (6 phases with week ranges)
- Area listing (12 areas) with sub-areas, each with status marker
- Counters section (total concepts, design notes, open questions)
- Recent sessions section

Content:
```markdown
---
last-updated: 2026-03-24
---

# Seedlight Study Dashboard

## Visao Geral

| Fase | Nome | Semanas | Status |
|------|------|---------|--------|
| 1 | Fundacao Conceitual | 1-4 | nao iniciada |
| 2 | Hardware e Modelos Pequenos | 5-8 | nao iniciada |
| 3 | Agentes, GraphRAG e Arquitetura | 9-12 | nao iniciada |
| 4 | Infra Offline e Estudos de Caso | 13-16 | nao iniciada |
| 5 | Treinamento e Integracao | 17-20 | nao iniciada |
| 6 | Prototipo Completo | 21-24 | nao iniciada |

---

## Areas de Estudo

### Fase 1 — Fundacao Conceitual (Semanas 1-4)

**Area 1 — Ciencias da Aprendizagem**
- [ ] 1.1 Teorias Fundamentais (Piaget, Vygotsky, Papert)
- [ ] 1.2 Aprendizagem Adaptativa e Personalizada
- [ ] 1.3 Avaliacao e Medicao de Aprendizagem

**Area 6 — Equidade Algoritmica e Justica em IA**
- [ ] 6.1 Fundamentos de Fairness em ML
- [ ] 6.2 Bias em IA Educacional
- [ ] 6.3 Auditoria de Bias

### Fase 2 — Hardware e Modelos Pequenos (Semanas 5-8)

**Area 5 — Modelos Pequenos e Inferencia em Dispositivos**
- [ ] 5.1 Quantizacao de Modelos
- [ ] 5.2 Modelos Candidatos para o Dispositivo
- [ ] 5.3 Treinamento com Reinforcement Learning

**Area 2 — Inteligencia Artificial para Educacao (AIED)**
- [ ] 2.1 Intelligent Tutoring Systems
- [ ] 2.2 Knowledge Tracing (BKT, DKT, SAKT, AKT)
- [ ] 2.3 Open Learner Models
- [ ] 2.4 LLMs em Educacao

### Fase 3 — Agentes, GraphRAG e Arquitetura (Semanas 9-12)

**Area 3 — Grafos de Conhecimento e Modelagem Curricular**
- [ ] 3.1 Knowledge Graphs — Fundamentos
- [ ] 3.2 Knowledge Graphs Educacionais
- [ ] 3.3 GraphRAG — Motor de Retrieval

**Area 4 — Arquitetura de Agentes com Primitivas Simples**
- [ ] 4.1 Building Effective Agents (Anthropic)
- [ ] 4.2 Memoria Persistente para o Companion
- [ ] 4.3 Retrieval no Dispositivo: GraphRAG Local
- [ ] 4.4 Estudo de Caso: OpenCode

### Fase 4 — Infra Offline e Estudos de Caso (Semanas 13-16)

**Area 7 — Privacidade de Dados e Soberania do Aprendiz**
- [ ] 7.1 Legislacao e Frameworks (LGPD, GDPR, COPPA, FERPA)
- [ ] 7.2 Privacy-Preserving ML
- [ ] 7.3 Portabilidade e Soberania Local

**Area 8 — Infraestrutura Offline-First e Edge Computing**
- [ ] 8.1 Estudo de Caso: Kolibri
- [ ] 8.2 Estudo de Caso: Project N.O.M.A.D.
- [ ] 8.3 Stack Completa de ML no Dispositivo
- [ ] 8.4 Software Offline-First (CRDTs, Automerge)
- [ ] 8.5 Raspberry Pi como Plataforma de Dev
- [ ] 8.6 Redes Mesh e Conectividade Comunitaria

**Area 9 — Padroes Abertos em Educacao**
- [ ] 9.1 Padroes Existentes (xAPI, LTI, Open Badges)
- [ ] 9.2 Protocolos de Integracao de IA (MCP, OpenAPI)

### Fase 5 — Treinamento e Integracao (Semanas 17-20)

**Area 10 — Modelagem Preditiva de Tendencias**
- [ ] 10.1 Analise de Tendencias
- [ ] 10.2 Labor Market Intelligence

**Area 11 — Design e UX para Criancas**
- [ ] 11.1 Design para Criancas
- [ ] 11.2 Interfaces para Baixa Literacia Digital
- [ ] 11.3 Visualizacao do Mapa Cognitivo

**Area 12 — Engenharia de Software e Arquitetura**
- [ ] 12.1 Arquitetura do Dispositivo Seedlight
- [ ] 12.2 Referencias de Arquitetura
- [ ] 12.3 Infraestrutura de ML

### Fase 6 — Prototipo Completo (Semanas 21-24)

- [ ] Integracao de todos os componentes
- [ ] Teste com crianca real
- [ ] Documentacao para release publico

---

## Contadores

- **Sources estudadas:** 0
- **Conceitos registrados:** 0
- **Design notes:** 0
- **Duvidas abertas:** 0
- **Conexoes no grafo:** 0

## Sessoes Recentes

*Nenhuma sessao registrada ainda.*
```

- [ ] **Step 2: Commit**

```bash
git add seedlight-vault/dashboard.md
git commit -m "feat: add study dashboard with full guide structure"
```

---

### Task 4: Create /study Skill

**Files:**
- Create: `.claude/skills/study/SKILL.md`

- [ ] **Step 1: Create skill directory**

```bash
mkdir -p /Users/robson/Desktop/dev/seedlight/.claude/skills/study
```

- [ ] **Step 2: Create SKILL.md**

Create `.claude/skills/study/SKILL.md`:
```markdown
---
name: study
description: Inicia sessao de estudo do Seedlight. Use quando for estudar um paper, repo, livro ou conceito do guia de estudos.
---

# Sessao de Estudo — Seedlight

Voce esta iniciando uma sessao de estudo conjunto para o projeto Seedlight.

## Setup da Sessao

1. Leia `seedlight-vault/dashboard.md` para saber o progresso atual
2. Leia a entry mais recente de `seedlight-vault/journal/` (o arquivo com data mais recente) para recuperar contexto da ultima sessao
3. Verifique se a ultima sessao teve `/review`. Se nao, alerte o usuario e proponha rodar `/review` primeiro
4. Pergunte ao usuario o que ele quer estudar hoje. Se ele trouxer um paper/repo, ofereca para criar a nota de Source

## Durante o Estudo

- Leia o material junto com o usuario (PDFs via Read tool, repos via WebFetch ou Agent)
- Atue como mentor: questione entendimentos, faca perguntas socraticas, aponte quando algo parece errado. NAO concorde por conveniencia
- Quando surgir um conceito relevante para o Seedlight, proponha: "Isso parece um [kind] — quer que eu registre com /insight?"
- Quando perceber conexao com conceito ja registrado no vault, aponte a conexao

## Criando uma Source Note

Se for material novo, crie a nota de source no vault:
- Papers: `seedlight-vault/sources/papers/autor-ano-titulo-curto.md`
- Repos: `seedlight-vault/sources/repos/nome-do-repo.md`
- Livros: `seedlight-vault/sources/books/titulo-curto.md`

Use o template correspondente de `seedlight-vault/templates/`. Preencha os campos do frontmatter.

## Convencoes

- Nomes de arquivo: kebab-case, lowercase, sem acentos
- Frontmatter: consulte CLAUDE.md para campos validos
- Links: NUNCA criar link sem frase que explique POR QUE o link existe
- Tags: vocabulario fechado (ver CLAUDE.md), maximo 3-4 por nota

## Referencia

- Guia de estudos: `docs/seedlight-study-guide-v3.md`
- Spec completa: `docs/superpowers/specs/2026-03-24-study-tracking-system-design.md`
- Vault: `seedlight-vault/`
```

- [ ] **Step 3: Verify skill loads**

```bash
ls -la .claude/skills/study/SKILL.md
```

- [ ] **Step 4: Commit**

```bash
git add .claude/skills/study/
git commit -m "feat: add /study skill for starting study sessions"
```

---

### Task 5: Create /insight Skill

**Files:**
- Create: `.claude/skills/insight/SKILL.md`

- [ ] **Step 1: Create skill directory**

```bash
mkdir -p /Users/robson/Desktop/dev/seedlight/.claude/skills/insight
```

- [ ] **Step 2: Create SKILL.md**

Create `.claude/skills/insight/SKILL.md`:
```markdown
---
name: insight
description: Registra um insight no vault do Seedlight com classificacao e links. Use durante sessoes de estudo quando surgir um conceito ou decisao de design relevante.
---

# Registrar Insight — Seedlight

O usuario quer registrar um insight no vault. Pode ser um conceito extraido de um paper, um padrao arquitetural de um repo, uma decisao de design, ou qualquer conhecimento relevante para o Seedlight.

## Fluxo

1. **Receba o insight** — o usuario descreve ou voce propoe baseado na conversa
2. **Classifique:**
   - `kind`: principle | framework | metric | pattern | antipattern | sequence | technique | constraint | case-study | lesson
   - `seedlight-component`: companion | curriculum | bkt | graphrag | context-adapter | engagement | equity-layer | orchestrator | ui | infra | all
   - Pergunte ao usuario se a classificacao nao for obvia
3. **Busque conexoes** — leia o frontmatter das notas existentes em `seedlight-vault/concepts/` e `seedlight-vault/design/` para identificar notas que podem se conectar
4. **Decida o tipo de nota:**
   - Se e um conceito extraido de estudo → `concepts/nome-do-conceito.md`
   - Se e uma decisao/hipotese de design para o Seedlight → `design/componente-decisao.md`
5. **Crie a nota** usando o template de `seedlight-vault/templates/concept.md` ou `design.md`
6. **Escreva o conteudo** com links contextualizados para notas relacionadas. Cada link deve estar dentro de uma frase que explica a relacao
7. **Atualize notas relacionadas** — se faz sentido, adicione um backlink com contexto nas notas existentes que se conectam
8. **Atualize dashboard.md** — incremente o contador relevante em `seedlight-vault/dashboard.md`

## Convencoes

- Nomes de arquivo: kebab-case, lowercase, sem acentos
- NUNCA criar link sem frase que explique a relacao
- Links em prosa contextualizada, NUNCA em listas soltas
- Tags: vocabulario fechado (ver CLAUDE.md), maximo 3-4 por nota
- Cada nota de concept DEVE ter a secao "Por que importa para o Seedlight" — se nao importa, talvez nao mereca uma nota

## Referencia

- Spec: `docs/superpowers/specs/2026-03-24-study-tracking-system-design.md`
- Vault: `seedlight-vault/`
```

- [ ] **Step 3: Commit**

```bash
git add .claude/skills/insight/
git commit -m "feat: add /insight skill for recording study insights"
```

---

### Task 6: Create /review Skill

**Files:**
- Create: `.claude/skills/review/SKILL.md`

- [ ] **Step 1: Create skill directory**

```bash
mkdir -p /Users/robson/Desktop/dev/seedlight/.claude/skills/review
```

- [ ] **Step 2: Create SKILL.md**

Create `.claude/skills/review/SKILL.md`:
```markdown
---
name: review
description: Revisao de fim de sessao de estudo. Extrai insights nao registrados, cria journal entry, atualiza dashboard. Use ao final de cada sessao de estudo.
disable-model-invocation: true
---

# Review de Sessao — Seedlight

Voce esta encerrando uma sessao de estudo. Este review garante que nenhum insight se perca.

## Fluxo

1. **Releia a conversa** — percorra toda a conversa da sessao atual
2. **Identifique insights nao registrados** — conceitos discutidos, conexoes percebidas, decisoes de design sugeridas que NAO foram salvos com /insight
3. **Proponha cada um** — para cada insight nao registrado, proponha ao usuario:
   - O que e o insight
   - Classificacao sugerida (kind, seedlight-component)
   - Conexoes com notas existentes
   - Espere aprovacao antes de criar a nota
4. **Crie as notas aprovadas** — siga o mesmo processo do /insight
5. **Crie a journal entry** — em `seedlight-vault/journal/YYYY-MM-DD.md`:
   - Se ja existe entry para hoje, adicione a nova sessao no final do arquivo
   - Use o template de `seedlight-vault/templates/journal-entry.md`
   - Preencha: o que foi estudado, links para insights registrados, duvidas abertas, proximos passos sugeridos
6. **Atualize o dashboard** — em `seedlight-vault/dashboard.md`:
   - Marque sub-areas estudadas (mude `[ ]` para `[x]` se concluida, ou adicione nota de progresso)
   - Atualize contadores (sources, conceitos, design notes, duvidas)
   - Atualize a secao "Sessoes Recentes"
   - Atualize `last-updated` no frontmatter

## Convencoes

- Journal entry: uma por dia, sessoes acumulam
- Nome do arquivo journal: `YYYY-MM-DD.md`
- Links contextualizados em prosa, nunca listas soltas
- Seja honesto na revisao — aponte entendimentos que pareceram frageis

## Referencia

- Spec: `docs/superpowers/specs/2026-03-24-study-tracking-system-design.md`
- Vault: `seedlight-vault/`
```

- [ ] **Step 3: Commit**

```bash
git add .claude/skills/review/
git commit -m "feat: add /review skill for end-of-session review"
```

---

### Task 7: Create /progress Skill

**Files:**
- Create: `.claude/skills/progress/SKILL.md`

- [ ] **Step 1: Create skill directory**

```bash
mkdir -p /Users/robson/Desktop/dev/seedlight/.claude/skills/progress
```

- [ ] **Step 2: Create SKILL.md**

Create `.claude/skills/progress/SKILL.md`:
```markdown
---
name: progress
description: Mostra o progresso geral do estudo do Seedlight. Le o dashboard e apresenta visao geral de onde estamos.
disable-model-invocation: true
---

# Progresso de Estudo — Seedlight

O usuario quer ver o estado geral do estudo.

## Modo Padrao (rapido)

1. Leia `seedlight-vault/dashboard.md`
2. Apresente um resumo formatado:
   - Fase atual e progresso dentro dela
   - Areas concluidas vs em andamento vs nao iniciadas
   - Contadores (sources, conceitos, design notes, duvidas abertas)
   - Ultimas sessoes
3. Sugira a proxima area de estudo baseada na ordem do guia e dependencias

## Modo Recalculo (se o usuario pedir "recalcular" ou "recontar")

1. Leia TODOS os arquivos de `seedlight-vault/sources/`, `concepts/`, `design/`, `journal/`
2. Recontabilize tudo a partir do frontmatter
3. Reescreva `seedlight-vault/dashboard.md` com contadores atualizados
4. Apresente o resultado

## Referencia

- Guia de estudos: `docs/seedlight-study-guide-v3.md`
- Vault: `seedlight-vault/`
```

- [ ] **Step 3: Commit**

```bash
git add .claude/skills/progress/
git commit -m "feat: add /progress skill for study progress dashboard"
```

---

### Task 8: Update Study Guide with Research Discoveries

**Files:**
- Modify: `docs/seedlight-study-guide-v3.md`

- [ ] **Step 1: Update sqlite-vss reference to sqlite-vec**

In `docs/seedlight-study-guide-v3.md`, find the reference to sqlite-vss (around line 187) and update to sqlite-vec. Add note that sqlite-vss is deprecated.

- [ ] **Step 2: Add MiniRAG to Area 3.3**

After the LightRAG entry in Area 3.3, add:

```markdown
- **MiniRAG** — github.com/HKUDS/MiniRAG — Do mesmo time do LightRAG, desenhado especificamente para SLMs (modelos de 1.5B parametros). Usa apenas 25% do armazenamento do RAG tradicional. Grafo heterogeneo que combina chunks de texto + entidades nomeadas. Candidato forte para o dispositivo Seedlight.
```

- [ ] **Step 3: Add GRPO/veRL details to Area 5.3**

In the veRL entry in Area 5.3, add note about GRPO being the recommended algorithm (no value model needed, ~30-40% less memory than PPO).

- [ ] **Step 4: Add Aequitas insight to Area 6**

In Area 6.3, add note that Aequitas formalizes the distinction between assistive and punitive interventions, and that in education (assistive), the critical error is the false negative.

- [ ] **Step 5: Commit**

```bash
git add docs/seedlight-study-guide-v3.md
git commit -m "docs: update study guide with research discoveries (sqlite-vec, MiniRAG, GRPO, Aequitas)"
```

---

### Task 9: Initial Git Commit for Existing Files

**Files:**
- Stage: `README.md`, `ETHICS.md`, `VISION.md`, `CLAUDE.md`, `docs/`

- [ ] **Step 1: Stage existing project files**

```bash
git add README.md ETHICS.md VISION.md CLAUDE.md docs/
```

- [ ] **Step 2: Create initial commit**

Note: this should actually be the FIRST commit, run before all other tasks. Reorder execution accordingly.

```bash
git commit -m "feat: initial commit — Seedlight project docs, study guide, and system design spec"
```

---

### Task 10: Configure Review Reminder in CLAUDE.md

**Files:**
- Modify: `CLAUDE.md`

The spec requires a reminder mechanism for running `/review` at session end. Since Claude Code hooks are shell commands triggered by tool events (not semantic triggers), the most practical approach is a behavioral instruction in CLAUDE.md.

- [ ] **Step 1: Add review reminder section to CLAUDE.md**

Add after the "Ciclo de Vida da Sessao" section in CLAUDE.md:

```markdown
### Lembrete de Review

Ao final de conversas longas sobre estudo (quando o contexto esta ficando grande ou o usuario indica que vai encerrar), lembre de rodar `/review` se ainda nao foi feito na sessao. Alerte: "Quer que eu rode /review antes de encerrar? Garante que nenhum insight se perca."
```

- [ ] **Step 2: Update /synthesize reference**

In CLAUDE.md, change the `/synthesize` entry to clearly mark it as planned/future:

```markdown
- `/synthesize` — *(planejado, ainda nao implementado)* analise cruzada do vault
```

- [ ] **Step 3: Commit**

```bash
git add CLAUDE.md
git commit -m "docs: add review reminder instructions and clarify /synthesize status"
```

---

## Execution Order

Execute in this order:

1. **Task 9** — Initial commit of existing files (README, ETHICS, VISION, CLAUDE.md, docs/)
2. **Task 1** — Vault structure
3. **Task 2** — Templates
4. **Task 3** — Dashboard
5. **Task 4** — /study skill
6. **Task 5** — /insight skill
7. **Task 6** — /review skill
8. **Task 7** — /progress skill
9. **Task 8** — Update study guide with discoveries
10. **Task 10** — Configure review reminder and clarify /synthesize

**Notes:**
- Task 9 executes first despite its number — it commits pre-existing files before new work begins
- `/review` and `/progress` skills have `disable-model-invocation: true` because they should only be user-triggered (not auto-invoked by Claude during conversation)
- `/study` and `/insight` do NOT have this flag because Claude may suggest invoking them during conversation
- CLAUDE.md was already updated with unified vocabulary in a prior session — no additional changes needed for spec step 6
- `/synthesize` skill is intentionally not created yet (spec marks it as future)
