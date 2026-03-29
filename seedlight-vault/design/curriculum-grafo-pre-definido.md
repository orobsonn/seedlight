---
seedlight-component: curriculum
status: hypothesis
based-on: ["[[construcionismo]]", "[[zona-desenvolvimento-proximal]]"]
tags: [foundational, open-question]
---

# Emergent Curriculum — Grafo Pre-definido, Caminho Emergente

## Decisao / Hipotese

O Emergent Curriculum nao significa "sem curriculo". O **grafo de conhecimento** (conceitos e relacoes) e pre-definido — o que existe pra aprender esta mapeado no GraphRAG. O que emerge da crianca e o **caminho** pelo grafo: a sequencia, o ritmo e o contexto em que cada conceito e encontrado.

Analogia: o mapa existe, mas a rota e da crianca.

## Fundamentacao

Sem grafo pre-definido, o sistema nao sabe o que precisa ensinar e a avaliacao fica impossivel — nao ha como medir progresso sem saber progresso em direcao a que. O ECD (Mislevy) exige um Student Model com variaveis definidas; essas variaveis sao os nos do grafo.

O Context Adapter adapta o contexto (como o conceito aparece), mas o conceito em si precisa existir no grafo antes.

## Trade-offs

- **Quem define o grafo?** Precisa de curadoria humana? Pode ser gerado? Segue algum curriculo nacional (BNCC)?
- **Granularidade** — grafo muito fino e impossivel de manter; muito grosso e impreciso pra avaliacao
- **Rigidez vs emergencia** — o grafo pre-definido pode limitar a emergencia se for seguido de forma rigida. O orchestrator precisa tratar o grafo como mapa de possibilidades, nao como trilho

## Status

Hipotese. Decisoes sobre fonte do grafo, granularidade e formato serao exploradas na Fase 3 (Area 3 — Knowledge Graphs).
