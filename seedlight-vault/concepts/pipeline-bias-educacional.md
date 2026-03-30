---
kind: framework
sources: ["[[kizilcec-lee-2022-fairness-education]]"]
seedlight-component: equity-layer
tags: [fairness, foundational]
---

# Pipeline de Bias em Sistemas Educacionais

## O que e

Framework de Kizilcec & Lee (2022) que identifica 4 etapas onde bias entra em sistemas educacionais adaptativos. Cada etapa tem um tipo de bias especifico e requer estrategia diferente de mitigacao:

| Etapa | Tipo de bias | Mecanismo |
|-------|-------------|-----------|
| 1 — Dados | **Measurement bias** | Instrumento de medicao nao mede a mesma coisa pra todos os grupos |
| 2 — Modelo | **Learning bias** | Modelo calibra parametros com base em dados enviesados da etapa 1 |
| 3 — Decisao | **Allocation bias** | Sistema oferece oportunidades desiguais de complexidade |
| 4 — Impacto | **Feedback loop** | Decisao enviesada gera dados enviesados no proximo ciclo |

A contribuicao central nao e listar tipos de bias (isso outros papers fazem), mas mostrar que **a etapa importa** — intervir no ponto errado nao resolve. Auditar so a saida (etapa 3) sem corrigir a entrada (etapa 1) mascara o problema, como cair na [[armadilhas-de-abstracao|Portability Trap]] de Selbst.

## Por que importa para o Seedlight

No Seedlight, o pipeline mapeia diretamente para componentes: Engagement Detector (etapa 1), BKT (etapa 2), Companion (etapa 3), e o ciclo longitudinal (etapa 4). A estrategia viavel no Pi 5 e intervencao proporcional — investimento pesado na etapa 1 (calibracao do sensor), auditoria batch na etapa 3, monitoramento passivo nas etapas 2 e 4. Detalhado em [[equity-layer-intervencao-proporcional]]. O [[feedback-loop-bias]] e especialmente perigoso num sistema que acompanha a crianca por anos.
