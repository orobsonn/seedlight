---
kind: principle
sources: ["[[kizilcec-lee-2022-fairness-education]]"]
seedlight-component: equity-layer
tags: [fairness, foundational]
---

# Representational Bias vs Historical Bias

## O que e

Taxonomia de Kizilcec & Lee (2022) que distingue duas fontes fundamentais de bias nos dados de sistemas educacionais:

**Representational bias** — grupos ausentes ou sub-representados no dataset de treinamento/calibracao. O modelo nunca viu esses perfis e extrapola de forma errada. Exemplo: calibrar BKT com dados de criancas urbanas de SP e implantar em comunidade ribeirinha no Amazonas.

**Historical bias** — todos os grupos estao representados nos dados, mas a metrica escolhida carrega suposicao cultural embutida. Os dados "parecem corretos" porque refletem a realidade fielmente — mas a realidade ja contem desigualdade. Exemplo: usar tempo de resposta como proxy de competencia quando em algumas culturas pausar pra pensar e valorizado.

A distincao e critica porque **as solucoes sao diferentes**: representational bias se resolve com coleta mais diversa; historical bias exige repensar o que esta sendo medido. Confundir os dois leva a investir na solucao errada — coletar mais dados nao resolve um problema de metrica enviesada.

## Por que importa para o Seedlight

O Emergent Curriculum amplifica ambos os tipos. Representational: o sistema vai ser calibrado com algum grupo inicial e implantado em contextos diferentes. Historical: contexto socioeconomico da crianca (fome, cansaco, instabilidade familiar) pode virar proxy de capacidade cognitiva se o sistema nao distinguir estado temporario de competencia — detalhado em [[companion-estado-vs-capacidade]]. O engagement detector e particularmente vulneravel a measurement bias cultural, como expressoes emocionais variando entre culturas e perfis neurodivergentes, risco ja identificado em [[armadilhas-de-abstracao]].
