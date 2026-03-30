---
type: repo
areas: ["6.3"]
status: done
date: 2026-03-30
tags: [fairness]
---

# Aequitas — Bias and Fairness Audit Toolkit

## Resumo Pratico

Toolkit de auditoria de fairness da University of Chicago. Diferencial: comeca pelo **contexto de uso** (assistivo vs punitivo) pra derivar qual metrica priorizar, em vez de comecar pela matematica. Em intervencao assistiva (educacao), falso negativo e o erro critico. Fairlearn (Microsoft) foca em mitigacao, AIF360 (IBM) e toolkit completo mais academico, Aequitas foca em contexto.

## Conceitos Extraidos

- [[aequitas-contexto-assistivo]] — distincao assistivo vs punitivo como ponto de partida

## Uso no Seedlight

Primeiro na pipeline de auditoria ([[equity-layer-pipeline-auditoria]]): Aequitas define o framework, Fairlearn mitiga, AIF360 complementa.
