---
seedlight-component: companion
status: hypothesis
based-on: ["[[two-sigma-problem]]"]
tags: [foundational, scaffolding]
---

# Companion — Mapeamento dos Mecanismos de Tutoria

## Decisao / Hipotese

O Longitudinal Companion deve replicar os 4 mecanismos do tutor humano identificados por Bloom, distribuindo a responsabilidade entre componentes especializados em vez de depender apenas do LLM:

| Mecanismo | Componente | Viabilidade |
|-----------|-----------|-------------|
| Feedback imediato | LLM | Alta, mas qualidade limitada pelo tamanho do modelo |
| Pacing adaptativo | BKT | Alta — BKT e leve e roda em qualquer hardware |
| Diagnostico continuo | BKT + analise de padroes | Media — requer distinguir "entendeu" de "decorou" |
| Engajamento | Context Adapter + UI | Baixa — competir com YouTube/TikTok e o desafio existencial |

## Fundamentacao

O [[two-sigma-problem]] demonstra que esses 4 mecanismos explicam o ganho de 2 sigma. O Seedlight nao precisa replicar todos perfeitamente — se conseguir 1 sigma (mastery learning em grupo ja atinge isso segundo Bloom), ja e transformador. A arquitetura distribui a carga: o LLM e a interface conversacional, mas o BKT e o cerebro de pacing e diagnostico, e o Context Adapter e o motor de engajamento.

## Trade-offs

- Modelos pequenos (1-3B) podem nao dar feedback correto em todas as materias — tensao entre offline-first e qualidade. Pode ser necessario modelos maiores ou hardware mais robusto
- O pacing adaptativo depende de como o sistema verifica dominio — a tensao entre checkpoints explicitos e inferencia fluida e explorada em [[companion-checkpoints-vs-inferencia]]
- Engajamento via interface adaptativa (chat que vira jogo, slides, etc.) e visao de futuro — MVP deve focar em interface de chat com elementos visuais adaptativos. A questao mais profunda e se engajamento vem de mecanicas ou de vinculo, explorada em [[engagement-vinculo-vs-coercao]]
- Diagnostico sem sinais nao-verbais (tom de voz, expressao facial) e inerentemente limitado — BKT compensa parcialmente com analise longitudinal

## Status

Hipotese a ser validada durante prototipagem (Fase 6). Os componentes individuais serao estudados nas areas 2.2 (BKT), 4.1 (agentes), e 5.1-5.2 (modelos pequenos).
