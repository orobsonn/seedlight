---
type: paper
areas: ["6.2"]
status: done
date: 2026-03-30
authors: ["Rene Kizilcec", "Hansol Lee"]
year: 2022
tags: [fairness, assessment]
---

# Algorithmic Fairness in Education — Kizilcec & Lee (2022)

## Resumo Pratico

Framework que mapeia como bias entra e se amplifica em sistemas educacionais adaptativos. A contribuicao central e o pipeline de 4 etapas (dados → modelo → decisao → impacto) onde cada etapa tem tipo de bias especifico e requer estrategia diferente de mitigacao. Distinguem dois tipos fundamentais de bias nos dados: representational (grupos ausentes) e historical (metrica carrega suposicao cultural). O feedback loop entre etapa 4 e etapa 1 e identificado como o mecanismo mais perigoso em sistemas longitudinais.

## Conceitos Extraidos

- [[pipeline-bias-educacional]] — framework de 4 etapas que organiza onde bias entra em sistemas adaptativos, com tipo de bias e estrategia de mitigacao por etapa
- [[representational-vs-historical-bias]] — taxonomia de bias nos dados. Representational e ausencia de grupos no dataset; historical e metrica que absorve desigualdade existente. Problemas diferentes exigem solucoes diferentes
- [[feedback-loop-bias]] — decisao enviesada gera dados enviesados no ciclo seguinte, criando espiral de subestimacao. E a [[armadilhas-de-abstracao|Ripple Effect Trap]] operando dentro do proprio sistema

## Citacoes-Chave

- Bias em sistemas adaptativos nao e um unico problema — e um pipeline onde cada etapa requer intervencao especifica
- Historical bias e mais traicoeiro que representational porque os dados "parecem corretos" — refletem a realidade fielmente, mas a realidade ja contem desigualdade
- Em sistemas longitudinais, feedback loops transformam bias pontual em dano acumulado ao longo de anos

## Duvidas Abertas

- Como distinguir estado temporario (cansaco, fome) de padrao persistente numa crianca?
- Como validar measurement bias no Engagement Detector sem dados reais de populacoes diversas?
