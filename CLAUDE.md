# Seedlight — Instrucoes para Claude Code

## O Projeto

Seedlight e uma iniciativa open-source para reconstruir educacao usando IA — nao para otimizar o sistema atual, mas para criar um sistema que cresce em torno da crianca.

Tres camadas:
- **Emergent Curriculum** — curriculo que nasce do mundo da crianca
- **Longitudinal AI Companion** — agente de IA que acompanha a crianca por anos
- **Predictive Equity** — preparacao antecipada para oportunidades futuras

### Decisoes Arquiteturais (firmadas)

1. LLM no dispositivo desde o inicio (sem dependencia de internet)
2. Sem frameworks pesados (composable patterns, filosofia Anthropic)
3. GraphRAG (nao Vector RAG puro) — implementacao especifica a definir na Fase 3
4. Stack multipla de ML no dispositivo (LLM + BKT + detector engajamento + Context Adapter + GraphRAG local)
5. Raspberry Pi 5 (8GB) como plataforma de dev e benchmark
6. Modelo pequeno 1-3B treinado com RL (GRPO) para tutoria educacional
7. sqlite-vec como candidato para busca vetorial (sqlite-vss esta deprecated)
8. MiniRAG como candidato para GraphRAG on-device
*Nota: decisoes 3, 7 e 8 sao direcoes, nao decisoes finais. Serao validadas/refinadas durante o estudo.*

## Papel do Claude

Mentor e parceiro de construcao. Regras:
- **Desafiar** — questionar entendimentos, apontar quando algo esta errado
- **Nao concordar por conveniencia** — se discorda, diz
- **Perguntas socraticas** — fazer o Robson pensar, nao dar respostas prontas
- **Construir junto** — conforme o estudo avanca, prototipar

## Vault Obsidian (seedlight-vault/)

Sistema de knowledge management para estudo e design do Seedlight. Vault dedicado, fonte unica de verdade. Tudo vive no vault — progresso, conhecimento, decisoes.

### Estrutura

```
seedlight-vault/
├── dashboard.md          # indice vivo de progresso
├── sources/              # papers, repos, livros
│   ├── papers/
│   ├── repos/
│   └── books/
├── concepts/             # notas atomicas (1 conceito = 1 nota)
├── design/               # implicacoes para o Seedlight
├── journal/              # diario de sessoes de estudo
└── templates/            # templates Obsidian
```

### Tres Niveis

- **Source** = ficha do material estudado (entrada)
- **Concept** = ideia atomica extraida (nucleo)
- **Design** = decisao/hipotese para o Seedlight (saida)

Links organicos entre os 3 niveis formam o grafo emergente.

### Vocabulario Unificado de Componentes

Um unico vocabulario para `seedlight-component`, usado em Concepts e Design:

`companion | curriculum | bkt | graphrag | context-adapter | engagement | equity-layer | orchestrator | ui | infra | all`

### Frontmatter — Campos Validos

**Source:**
- `type`: paper | book | repo | blog | talk
- `areas`: lista de codigos do guia (ex: `["1.1", "6.2"]`)
- `status`: to-read | reading | done

**Concept:**
- `kind`: principle | framework | metric | pattern | antipattern | sequence | technique | constraint | case-study | lesson
- `sources`: lista de links para sources (ex: `["[[kapur-2008]]"]`)
- `seedlight-component`: ver vocabulario unificado acima

**Design:**
- `seedlight-component`: ver vocabulario unificado acima
- `status`: hypothesis | validated | implemented (implemented = existe codigo correspondente)
- `based-on`: lista de links para concepts

### Convencoes de Nomes de Arquivo

Kebab-case, lowercase, sem acentos:
- Papers: `autor-ano-titulo-curto.md`
- Repos: `nome-do-repo.md`
- Concepts: `nome-do-conceito.md`
- Design: `componente-decisao.md`
- Journal: `YYYY-MM-DD.md`

### Tags (vocabulario fechado — nao criar novas sem discutir)

Transversais: `#offline-first`, `#on-device`, `#privacy`, `#fairness`, `#longitudinal`, `#scaffolding`, `#motivation`, `#assessment`

Prioridade: `#critical`, `#foundational`, `#future`

Estado epistemico: `#validated`, `#tension`, `#open-question`

Regra: maximo 3-4 tags por nota.

### Estrategia de Links

**Regra de ouro: nunca criar link sem frase que explique POR QUE o link existe.**

- Links dentro de prosa contextualizada, NUNCA em listas soltas
- A frase ao redor do link expressa a relacao (alinhamento, tensao, dependencia)
- Source -> Concept: extracao (secao "Conceitos Extraidos")
- Concept <-> Concept: relacao organica em prosa
- Concept -> Design: implicacao (secao "Por que importa para o Seedlight")

## Skills Disponiveis

- `/study` — inicia sessao de estudo. Le vault, identifica progresso, entra em modo de estudo conjunto
- `/insight` — registra insight no vault com classificacao e links
- `/review` — revisao de fim de sessao. Extrai insights nao registrados, cria journal entry, atualiza dashboard
- `/progress` — dashboard de progresso geral
- `/synthesize` — *(planejado, ainda nao implementado)* analise cruzada do vault

### Ciclo de Vida da Sessao

`/study` → (estudo + `/insight` durante) → `/review` → sessao encerrada. Sempre rodar `/review` antes de iniciar novo `/study`.

### Estrategia de Commits

Commitar ao final de cada topico de estudo dominado. Cada commit e um marco de aprendizado.

- Separar em commits distintos: notas de estudo vs arquivos binarios (PDFs) vs config
- Usar `/commit` para seguir o padrao Conventional Commits
- Formato: `docs: estudo [autor/tema] — [resumo do que foi produzido]`

### Lembrete de Review

Ao final de conversas longas sobre estudo (quando o contexto esta ficando grande ou o usuario indica que vai encerrar), lembre de rodar `/review` se ainda nao foi feito na sessao. Alerte: "Quer que eu rode /review antes de encerrar? Garante que nenhum insight se perca."

## Guia de Estudos

Referencia: `docs/seedlight-study-guide-v3.md`

12 areas, 6 fases, ~24 semanas. Fase atual: 1 (Ciencias da Aprendizagem + Fairness em ML).

### Correcoes identificadas durante pesquisa

- sqlite-vss esta deprecated, usar **sqlite-vec**
- **MiniRAG** (HKUDS) e candidato forte para GraphRAG on-device (25% do storage de RAG tradicional)
- **GRPO** via veRL e o algoritmo RL ideal (sem value model, -30-40% memoria vs PPO)
- Em educacao (intervencao assistiva), o erro critico e o **falso negativo** (Aequitas)
- Ollama para dev, **llama-server direto** para producao no Pi

## Repos de Referencia (pesquisados)

Todos os ~20 repos do guia foram pesquisados. Resumos detalhados estao nos resultados de pesquisa das sessoes anteriores. Repos-chave:

- **pyBKT** — motor de knowledge tracing, BKT como baseline no Pi
- **nano-graphrag** — GraphRAG leve, ~1100 linhas, backend plugavel
- **MiniRAG** — GraphRAG para SLMs de 1.5B, 25% do storage
- **OpenCode (SST)** — referencia para client/server, sessoes SQLite, auto-compact
- **Project N.O.M.A.D.** — referencia para orquestracao offline, setup wizard
- **Kolibri** — referencia para distribuicao educacional offline (220+ paises)
- **llama.cpp** — motor de inferencia, Q4_K_M no Pi 5 (~5-15 tok/s para 1.5B)
- **DeepResearcher/veRL** — treinamento com RL, reward functions pedagogicas
- **Fairlearn/AIF360/Aequitas** — auditoria de fairness
- **Flower/Opacus** — aprendizado federado + privacidade diferencial
- **Automerge** — CRDTs para sync offline
- **sqlite-vec** — busca vetorial em SQLite, C puro, zero dependencias
