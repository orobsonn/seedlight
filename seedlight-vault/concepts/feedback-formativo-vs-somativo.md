---
kind: principle
sources: ["[[liang-2023-llm-assessment]]"]
seedlight-component: companion
tags: [assessment, foundational]
---

# Feedback Formativo vs Somativo (Liang 2023)

## O que e

Liang et al. estudaram os limites de LLMs em avaliacao e feedback educacional. O achado central: LLMs sao bons em feedback **formativo** (qualitativo, direcional) e ruins em feedback **somativo** (nota, classificacao, certo/errado preciso).

- **Formativo:** "Sua explicacao sobre por que chove mostra que voce entende evaporacao mas confunde condensacao com precipitacao" → LLM faz bem. E dialogo, adaptacao de linguagem, identificacao qualitativa de gaps — territorio natural do modelo de linguagem
- **Somativo:** "Voce domina 73% do ciclo da agua" → LLM nao deveria fazer isso. Requer modelo explicito do aluno, tracking persistente, estimativa calibrada — territorio do [[bkt-mecanica]]

Alerta critico: em dominios abertos (ciencias, historia, contextos imprevisiveis), LLMs dando feedback inventam coisas com confianca. Em matematica fechada e detectavel. Em conteudo emergente — exatamente o tipo que o Seedlight gera — e muito mais perigoso.

## Por que importa para o Seedlight

Confirma a divisao de trabalho na arquitetura: BKT faz o somativo (tracking preciso de P(dominio) por skill), LLM faz o formativo (dialogo, explicacao, feedback qualitativo). O [[its-estrategista-executor]] garante que o LLM nao tenta fazer o que nao sabe — o harness consulta o BKT e monta a estrategia, o LLM executa via dialogo.

O risco de hallucination em dominios abertos reforca a necessidade de GraphRAG como fonte de verdade: o LLM so responde sobre conteudo educacional que encontrou no grafo. Se nao encontrou, diz que nao sabe. Isso e o oposto do comportamento padrao de LLMs.
