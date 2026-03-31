---
kind: pattern
sources: ["[[corbett-anderson-1995-bkt]]"]
seedlight-component: bkt, graphrag
tags: #foundational
---

# BKT + GraphRAG — Compensacao Mutua de Fraquezas

## O que e

O BKT trata cada skill como independente — nao sabe que "fracao com denominador igual" e "fracao com denominador diferente" sao relacionadas. Essa e sua principal limitacao, e o que motivou a criacao de DKT, SAKT e AKT (que capturam dependencias entre skills via deep learning, mas ao custo de interpretabilidade, dados e hardware).

O GraphRAG resolve essa limitacao sem trocar o modelo de KT: o **grafo de conhecimento** sabe as relacoes entre conceitos (pre-requisitos, dependencias, similaridades). O BKT rastreia dominio de cada skill individualmente, e o grafo contextualiza essas estimativas dentro da estrutura curricular.

Exemplo: a crianca tem P(dominio) = 0.95 em "fracao denominador igual" e 0.1 em "fracao denominador diferente". O BKT sozinho nao ve relacao. O GraphRAG sabe que o segundo depende do primeiro e que a transicao e o proximo passo natural.

## Por que importa para o Seedlight

Permite manter BKT como motor primario (leve, interpretavel, poucos dados) sem perder a capacidade de capturar relacoes entre conceitos. A alternativa seria migrar pra modelos de deep learning (DKT/SAKT/AKT) que exigem mais dados, mais hardware e perdem interpretabilidade — tudo que o Seedlight nao pode pagar no Pi 5.

E uma solucao arquitetural (dois componentes simples que se complementam) em vez de uma solucao de modelo (um componente complexo que faz tudo). Alinha com [[ml-classico-ia-generativa]].
