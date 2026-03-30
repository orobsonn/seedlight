---
kind: pattern
sources: ["[[kizilcec-lee-2022-fairness-education]]"]
seedlight-component: equity-layer, bkt, companion
tags: [fairness, critical, longitudinal]
---

# Feedback Loop de Bias

## O que e

Padrao identificado por Kizilcec & Lee (2022) onde a decisao enviesada de um ciclo gera dados enviesados para o ciclo seguinte, criando espiral de subestimacao (ou superestimacao) que se amplifica ao longo do tempo.

O mecanismo: se measurement bias na etapa 1 faz o sistema subestimar uma crianca, a etapa 3 oferece conteudo mais facil. A crianca responde bem (porque e facil demais), o BKT confirma o nivel baixo, e no proximo ciclo o sistema continua subestimando. Cada iteracao reforça a anterior.

E a [[armadilhas-de-abstracao|Ripple Effect Trap]] de Selbst operando dentro do proprio sistema — a intervencao (decisao enviesada) muda o contexto (dados do proximo ciclo) de forma que reforça o problema original.

## Por que importa para o Seedlight

O Seedlight e **longitudinal** — acompanha a crianca por anos. Um feedback loop que em sistemas de um semestre causa dano moderado, no Seedlight tem anos para se acumular. Uma crianca subestimada aos 6 pode chegar aos 10 com perfil de aprendizagem completamente distorcido — nao porque nao aprendeu, mas porque o sistema nunca ofereceu oportunidade. Isso viola diretamente [[equity-layer-fairness-metric|equal opportunity]], a metrica prioritaria do Seedlight. A estrategia de intervencao proporcional ([[equity-layer-intervencao-proporcional]]) prioriza a etapa 1 justamente para cortar o combustivel da espiral na origem.
