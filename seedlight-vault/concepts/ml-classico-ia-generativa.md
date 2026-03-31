---
kind: principle
sources: ["[[vanlehn-2011-its-effectiveness]]", "[[corbett-anderson-1995-bkt]]"]
seedlight-component: bkt, companion
tags: #foundational
---

# Complementaridade ML Classico + IA Generativa

## O que e

ML classico (BKT, classifiers, modelos probabilisticos) e IA generativa (LLMs) nao competem — se complementam. Cada um faz o que o outro nao consegue:

- **BKT**: tracking preciso de dominio por conceito, leve, interpretavel, funciona com poucos dados, auditavel para fairness
- **LLM**: compreensao de linguagem natural, dialogo, raciocinio em dominios abertos, feedback step-level sem enumerar caminhos

Tentar substituir um pelo outro e um erro. Um LLM nao consegue fazer knowledge tracing preciso e interpretavel. O BKT nao consegue conduzir um dialogo socratico.

O padrao [[its-estrategista-executor]] e a manifestacao arquitetural deste principio: o BKT (ML classico) informa a estrategia, o LLM (IA generativa) executa o dialogo.

## Por que importa para o Seedlight

Define a filosofia da stack de ML do dispositivo: nao e "um modelo que faz tudo", e uma **composicao de especialistas**. BKT para tracking, LLM para dialogo, engagement detector para sinais afetivos, GraphRAG para estrutura do conhecimento. Cada componente faz o que faz melhor, orquestrados pelo harness.
