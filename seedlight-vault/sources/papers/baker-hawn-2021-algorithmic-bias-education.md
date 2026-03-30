---
type: paper
areas: ["6.2"]
status: done
date: 2026-03-30
authors: ["Ryan Baker", "Adriana Hawn"]
year: 2021
tags: [fairness, assessment]
---

# Algorithmic Bias in Education — Baker & Hawn (2021)

## Resumo Pratico

Survey de casos reais de IA em educacao, categorizando quando amplificou e quando reduziu desigualdade. Descoberta central: a maioria das falhas documentadas esta na etapa 3 do pipeline (allocation bias), nao na etapa 1. Historical bias e mais prevalente que representational nos casos reais. Sistemas que funcionaram tinham humano no loop interpretando sinais no contexto. Principio derivado: autonomia do sistema deve ser proporcional a confianca do modelo.

## Conceitos Extraidos

- [[allocation-bias-prevalente]] — maioria das falhas reais em IA educacional e na decisao (etapa 3), nao nos dados (etapa 1). Historical bias mais comum que representational
- [[autonomia-proporcional-confianca]] — nivel de autonomia do sistema deve ser proporcional a confianca do modelo. Principio central dos casos de sucesso

## Casos Documentados

### Falhas

1. **Early warning systems** — universidades americanas sinalizavam alunos negros e de baixa renda como "em risco" usando proxies socioeconomicos (CEP, escola de origem), mesmo com desempenho igual. Historical bias: modelo absorveu desigualdade social como preditor.

2. **Automated Essay Scoring** — sistemas treinados com redacoes de alunos brancos de classe media penalizavam African American Vernacular English. Representational bias: modelo nunca viu variacao linguistica suficiente.

3. **Course recommendation** — sistemas sugeriam cursos mais faceis para determinados perfis demograficos, reduzindo exposicao a conteudo avancado. Historical bias: correlacao historica virou prescricao. Feedback loop amplificava.

### Sucessos

Casos de sucesso tinham algo em comum: **sistema informava humanos em vez de decidir sozinho**. O humano conhecia o contexto da crianca e distinguia estado temporario de capacidade — exatamente o que [[companion-estado-vs-capacidade]] precisa resolver.

## Duvidas Abertas

- O Seedlight nao tem humano garantido no loop — como resolver o dilema de que quem mais precisa do sistema e quem menos tem suporte humano?
