---
kind: sequence
sources: ["[[corbett-anderson-1995-bkt]]", "[[piech-2015-dkt]]", "[[pandey-karypis-2019-sakt]]", "[[ghosh-2020-akt]]"]
seedlight-component: bkt
tags: #foundational
---

# Knowledge Tracing — Evolucao BKT → DKT → SAKT → AKT

## O que e

Sequencia evolutiva de modelos de knowledge tracing ao longo de 25 anos:

| Modelo | Ano | Abordagem | Dados | Interpretavel | Custo |
|--------|-----|-----------|-------|---------------|-------|
| BKT | 1995 | 4 params/skill, Bayes | Dezenas | Sim | Trivial |
| DKT | 2015 | RNN, representacao latente | Milhares | Nao | Medio |
| SAKT | 2019 | Transformer, self-attention | Milhares | Nao | Medio |
| AKT | 2020 | Transformer + contexto | Milhares | Nao | Alto |

Cada geracao adicionou capacidade (capturar dependencias entre skills, contexto) mas perdeu interpretabilidade e aumentou custo computacional e necessidade de dados.

DKT (Piech 2015) teve problemas tecnicos serios — inconsistencias onde acerto *reduzia* P(dominio). Corrigido por Yeung & Yeung (2018).

SAKT e AKT resolvem a limitacao de skills independentes do BKT via self-attention, mas exigem milhares de sequencias de alunos pra treinar.

## Por que importa para o Seedlight

O trade-off fundamental e: BKT funciona com poucos dados (dia 1 de uso), e interpretavel (auditoria de fairness), e leve (Pi 5). Modelos mais avancados precisam de dados que so existem apos meses de uso. A estrategia e BKT como motor primario, com possibilidade de evolucao futura conforme dados acumulam — mas essa evolucao nao e necessidade presente.

A limitacao de skills independentes do BKT se resolve via GraphRAG (o grafo sabe as relacoes), nao trocando o modelo de KT.
