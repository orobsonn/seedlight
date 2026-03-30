---
kind: principle
sources: ["[[aequitas]]"]
seedlight-component: equity-layer
tags: [fairness, critical]
---

# Aequitas — Contexto Assistivo como Ponto de Partida

## O que e

Distincao central do framework Aequitas (University of Chicago): o tipo de intervencao determina qual erro e mais grave, e isso deve vir **antes** da escolha de metrica.

- **Intervencao punitiva** (justica criminal, negacao de credito) → falso **positivo** e pior (punir quem nao merece)
- **Intervencao assistiva** (educacao, saude) → falso **negativo** e pior (nao ajudar quem precisa)

Diferente de Fairlearn e AIF360 que perguntam "qual metrica voce quer otimizar?", Aequitas pergunta "qual e o tipo de intervencao?" e **deriva** a metrica a partir do contexto. Comeca pelo problema, nao pela matematica.

## Por que importa para o Seedlight

O Seedlight e intervencao assistiva — falso negativo (crianca que precisa de apoio mas nao e identificada) e o erro critico. Isso fundamentou a escolha de [[equity-layer-fairness-metric|equal opportunity como metrica prioritaria]]. Aequitas e a ferramenta que melhor encaixa no Seedlight por comecar pelo contexto. Pipeline de ferramentas detalhado em [[equity-layer-pipeline-auditoria]].
