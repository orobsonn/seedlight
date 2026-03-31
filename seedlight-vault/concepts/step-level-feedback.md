---
kind: principle
sources: ["[[vanlehn-2011-its-effectiveness]]", "[[koedinger-2007-cognitive-tutors]]"]
seedlight-component: companion, bkt
tags: #scaffolding, #foundational
---

# Feedback Step-Level

## O que e

Principio central da eficacia de ITS descoberto por VanLehn (2011): o fator que mais determina a eficacia de um sistema de tutoria nao e *quem* tutora (humano vs maquina), mas a **granularidade do feedback**.

- **Step-level feedback** (cada acao do aluno recebe resposta) → d = 0.76
- **Answer-level feedback** (so avalia a resposta final) → d = 0.31

A diferenca e massiva: 0.45 sigma. Sistemas como Duolingo operam no answer-level. O Cognitive Tutor de Koedinger operava no step-level e produziu resultados rigorosos em escala real por isso.

O desafio historico era que step-level feedback exigia model tracing — mapear todos os caminhos possiveis de resolucao. Isso so funcionava em dominios fechados (matematica, programacao). LLMs removem essa limitacao ao compreender raciocinio em linguagem natural.

## Por que importa para o Seedlight

O Companion deve operar no step-level, nao no answer-level. Isso significa acompanhar o *raciocinio* da crianca durante a atividade, nao esperar ela terminar pra dizer se acertou. O BKT informa o nivel de dominio, o harness decide o tipo de intervencao, e o LLM executa o feedback no passo certo — conforme o padrao [[its-estrategista-executor]].
