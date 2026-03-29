---
kind: constraint
sources: ["[[friedler-2016-impossibility-fairness]]"]
seedlight-component: equity-layer
tags: [fairness, foundational]
---

# Impossibilidade de Fairness

## O que e

Resultado formal de Friedler et al. (2016) demonstrando que definicoes matematicas de fairness sao mutuamente exclusivas — exceto em casos triviais, nao e possivel satisfazer todas simultaneamente.

Tres definicoes centrais:
- **Demographic Parity** — resultados iguais entre grupos
- **Equal Opportunity** — mesma taxa de acerto entre grupos (se sabe, o sistema reconhece)
- **Calibration** — probabilidades reportadas sao verdadeiras pra todos os grupos

A consequencia pratica e que qualquer sistema precisa fazer uma **escolha explicita** sobre qual definicao priorizar — e essa escolha nao e tecnica, e de valores.

## Por que importa para o Seedlight

O Seedlight escolheu priorizar equal opportunity, conforme documentado em [[equity-layer-fairness-metric]]. Isso significa garantir que o sensor (BKT + evidence rules) funciona bem pra todos os grupos — se a crianca sabe, o sistema reconhece, independente de como ela expressa conhecimento. Essa escolha se alinha com o principio de Aequitas de que em intervencao assistiva o erro mais grave e o falso negativo. Ao mesmo tempo, reforca o papel das [[armadilhas-de-abstracao]] como lembrete de que nenhuma metrica isolada captura fairness — a escolha de equal opportunity e necessaria mas insuficiente.
