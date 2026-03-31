---
kind: framework
sources: ["[[corbett-anderson-1995-bkt]]"]
seedlight-component: bkt
tags: #foundational, #assessment
---

# BKT — Mecanica dos 4 Parametros

## O que e

Bayesian Knowledge Tracing (Corbett & Anderson 1995) modela o conhecimento do aluno como Hidden Markov Model. Para cada skill, rastreia P(dominio) usando 4 parametros:

1. **P(L₀)** — Prior Knowledge — probabilidade de ja saber antes de qualquer interacao
2. **P(T)** — Transition/Learn — probabilidade de aprender a cada oportunidade de pratica
3. **P(G)** — Guess — probabilidade de acertar sem saber (chute)
4. **P(S)** — Slip — probabilidade de errar sabendo (escorregao)

A cada resposta, atualiza P(dominio) via Bayes. Acerto com P(G) baixo sobe muito. Acerto com P(G) alto sobe pouco.

**Vantagens**: interpretavel (cada parametro tem significado pedagogico), leve (multiplicacao de matrizes 2x2), poucos dados (dezenas de interacoes), calibravel por humano.

**Limitacoes**: trata skills como independentes (nao captura relacoes entre conceitos), sensivel ao design das questoes (5 questoes parecidas inflam P(dominio)), nao modela esquecimento temporal nativamente.

## Por que importa para o Seedlight

Motor primario do Learner Profile. A limitacao de skills independentes se compensa com o GraphRAG — o grafo sabe as relacoes entre conceitos, o BKT rastreia dominio de cada um. Juntos, suprem as fraquezas um do outro sem custo computacional adicional significativo.

Interpretabilidade e critica para [[model-cards]] e auditoria de fairness via [[equity-layer-pipeline-auditoria]] — voce consegue explicar *por que* o modelo acha que a crianca sabe ou nao.
