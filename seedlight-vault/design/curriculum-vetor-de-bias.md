---
seedlight-component: curriculum, equity-layer
status: hypothesis
based-on: ["[[armadilhas-de-abstracao]]", "[[curriculum-grafo-pre-definido]]"]
tags: [fairness, critical]
---

# Emergent Curriculum como Vetor de Bias

## Decisao / Hipotese

O Emergent Curriculum e simultaneamente a maior forca e o maior risco de fairness do Seedlight. Por design, criancas percorrem caminhos diferentes pelo grafo de conhecimento — sequencia, ritmo e contexto emergem do mundo da crianca. "Diferente" pode virar "desigual" sem que ninguem perceba.

### Risco Concreto

Uma crianca em contexto rural e outra em contexto urbano. O Context Adapter puxa contextos diferentes, o Companion gera atividades diferentes. O sistema pode oferecer problemas sistematicamente mais simples pra um grupo porque o contexto daquele grupo gera menos oportunidades de complexidade em certas areas.

Esse risco e estrutural — nao e bug, e consequencia direta do design. E por isso que nao pode ser resolvido apenas com metricas (framing trap de Selbst).

### Mitigacao Necessaria

- Monitoramento de equidade nas trajetorias: comparar profundidade e amplitude de cobertura do grafo entre subgrupos
- Grafo de conhecimento pre-definido ([[curriculum-grafo-pre-definido]]) garante que os **destinos** sao os mesmos — o que varia e o caminho
- Auditoria periodica de oportunidades de complexidade por contexto
- Alerta quando disparidade de progresso entre subgrupos exceder threshold (sem forcar convergencia artificial — ver [[equity-layer-fairness-metric]])

## Evidencia

Risco identificado durante estudo de Selbst et al. Mitigacao requer validacao com dados reais na Fase 6.
