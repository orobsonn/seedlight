---
seedlight-component: ui
status: hypothesis
based-on: ["[[open-learner-model]]", "[[olm-design-patterns]]", "[[stealth-assessment]]"]
tags: [assessment, motivation]
---

# OLM como Grafo Metacognitivo

## Decisao / Hipotese

O Learner Profile visivel do Seedlight deve ser um grafo conceitual negociavel — nao metricas numericas. A crianca ve nos (conceitos) e conexoes (relacoes), interage com eles, e pode discordar do que o sistema acha que ela sabe.

## Fundamentacao

Bull & Kay (2007) mostraram que OLMs negociaveis sao os mais eficazes porque o ato de discordar e metacognicao pura. Bodily (2018) confirmou que representacao conceitual (grafos) supera representacao numerica (barras). O Seedlight ja tem um grafo de conhecimento via GraphRAG — a estrutura de dados pra visualizacao ja existe.

O grafo evita o [[undermining-effect]]: nao ha numero pra perseguir, apenas relacoes pra explorar e nos que "acendem" quando a crianca domina. Alimenta autonomia (agencia sobre o modelo) e competencia (ve relacoes que construiu) sem criar motivacao extrinseca.

## Trade-offs

- **Complexidade visual:** o grafo completo pode ser tao denso quanto um dashboard. Precisa de filtragem inteligente — mostrar apenas o relevante pro momento
- **Negociacao com criancas pequenas:** uma crianca de 6 anos consegue discordar do modelo de forma significativa? O mecanismo de negociacao pode precisar variar por idade
- **Custo de renderizacao:** visualizacao de grafo interativa consome recursos — precisa ser leve no dispositivo

## Status

Hipotese. A forma concreta da interface (como o grafo e renderizado, como a negociacao funciona) sera definida na Area 11 (Design e UX para Criancas).
