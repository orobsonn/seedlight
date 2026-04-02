---
kind: pattern
sources: ["[[bodily-2018-olm-review]]"]
seedlight-component: ui
tags: [assessment, scaffolding]
---

# OLM Design Patterns (Bodily 2018)

## O que e

Bodily et al. fizeram revisao sistematica de Open Learner Models e separaram padroes que funcionam dos que falham.

### Padroes que funcionam

1. **Representacao conceitual** (grafos, mapas) > representacao numerica (barras, percentuais). Grafos mostram relacoes entre ideias, nao apenas quantidades
2. **Comparacao consigo mesmo** (seu eu de ontem) > comparacao com outros (leaderboards). Alimenta competencia sem competicao
3. **Acionavel** — o aluno ve o mapa e sabe o que fazer em seguida. O OLM nao so mostra estado, sugere direcao
4. **Simples** — menos informacao gera mais reflexao. Dashboards densos sobrecarregam

### Padroes que falham

1. **Dashboards densos** com muitas metricas — sobrecarga cognitiva, aluno ignora
2. **Leaderboards e comparacoes sociais** — alimentam motivacao extrinseca, prejudicam quem esta atras
3. **Visualizacoes incompreensiveis** — se o aluno nao entende o que ve, nao ha metacognicao

O principio unificador: o OLM existe pra provocar reflexao, nao pra informar. Tudo que atrapalha reflexao — complexidade, competicao, numeros — deve ser eliminado.

## Por que importa para o Seedlight

O Seedlight ja tem um grafo de conhecimento real (GraphRAG) com nos e conexoes. Bodily confirma que essa representacao e superior a barras de progresso. O desafio e manter simplicidade — o grafo completo pode ser tao denso quanto um dashboard cheio de metricas. A visualizacao precisa mostrar apenas o que e relevante pro momento da crianca, com caminho claro pro proximo passo. Isso conecta com [[open-learner-model]] (negociavel, metacognitivo) e [[trajetoria-vs-status]] (evolucao pessoal, nao snapshot).
