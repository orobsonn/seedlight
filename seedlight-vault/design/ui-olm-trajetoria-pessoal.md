---
seedlight-component: ui
status: hypothesis
based-on: ["[[trajetoria-vs-status]]", "[[open-learner-model]]", "[[motivacao-intrinseca-sdt]]"]
tags: [motivation, longitudinal]
---

# OLM com Trajetoria Pessoal

## Decisao / Hipotese

O OLM do Seedlight deve priorizar narrativa de evolucao pessoal sobre status atual. A crianca ve de onde veio, nao onde esta. Comparacao e sempre consigo mesma, nunca com outros.

## Fundamentacao

Matcha (2019) mostrou que dashboards de trajetoria alimentam competencia (SDT) sem criar motivacao extrinseca. O Seedlight tem vantagem unica aqui: como Companion longitudinal que acompanha a crianca por anos, acumula historico rico pra construir narrativa de evolucao. "Lembra quando voce nao sabia ler? Olha o que voce escreveu hoje" e mais poderoso que qualquer barra de progresso.

Bodily (2018) confirma: comparacao consigo mesmo > comparacao com outros. Leaderboards e rankings destroem motivacao dos que estao atras.

## Trade-offs

- **Memoria de longo prazo:** requer que o sistema mantenha snapshots historicos do Learner Profile pra poder mostrar evolucao — custo de armazenamento
- **Narrativa automatica:** gerar narrativa de trajetoria que seja significativa (nao generica) exige que o LLM tenha acesso ao historico e contexto da crianca
- **Primeiras semanas:** quando a crianca comeca, nao ha trajetoria pra mostrar. Precisa de estrategia pro cold start

## Status

Hipotese. Mecanismo concreto de visualizacao de trajetoria sera definido na Area 11.
