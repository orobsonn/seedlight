---
kind: framework
sources: ["[[bloom-1968-mastery-learning]]"]
seedlight-component: bkt
tags: [foundational, assessment]
---

# Mastery Learning

## O que e

Framework de Benjamin Bloom (1968) que inverte a logica da sala de aula convencional: em vez de fixar o tempo e variar o nivel de dominio, **fixa o nivel de dominio e varia o tempo**. Ninguem avanca sem dominar o pre-requisito.

O mecanismo opera em ciclos:

1. Ensina o topico
2. Avaliacao formativa (diagnostica, sem nota)
3. Quem dominou recebe enriquecimento; quem nao dominou recebe **correctives** — instrucao alternativa, nao repeticao da mesma explicacao
4. Nova avaliacao. Ciclo repete ate atingir criterio (tipicamente 80-90%)

Tres variaveis se ajustam: **tempo** (quanto a crianca precisa), **instrucao** (como ensinar — os correctives) e **criterio** (quando considerar que dominou). A sala convencional fixa as tres.

### Premissa radical sobre aptidao

Bloom redefiniu aptidao: nao e capacidade, e **velocidade**. Todos podem aprender a mesma coisa — uns precisam de mais tempo que outros. Quando a escola da o mesmo tempo pra todo mundo, transforma diferenca de velocidade em diferenca de resultado e chama isso de "talento".

### Resultados

Mastery Learning em sala de aula produziu ~1 sigma de melhoria sobre instrucao convencional. O [[two-sigma-problem]] (1984) mostrou que mesmo com mastery learning, ainda faltava 1 sigma pra igualar tutoria 1-a-1 — esse gap vem dos mecanismos do tutor (diagnostico continuo, scaffolding, engajamento) que o professor sozinho nao consegue replicar em escala.

## Por que importa para o Seedlight

Mastery Learning e a ponte entre a teoria (2 Sigma Problem) e a implementacao (Seedlight). Bloom provou que o principio funciona mas esbarrou na escala: o professor nao consegue criar avaliacoes formativas por unidade, diagnosticar individualmente, preparar correctives diferenciados e gerenciar ritmos diferentes simultaneamente. O Companion resolve as quatro barreiras — gera avaliacao dinamicamente, usa BKT pra diagnostico em tempo real, gera correctives via LLM, e cada crianca tem seu proprio Companion.

A premissa de que [[aptidao-como-velocidade|aptidao e velocidade, nao capacidade]] fundamenta por que o Companion nao deve tratar ritmo lento como sinal de problema. E a analise detalhada de como cada componente resolve as barreiras de escala esta em [[companion-4-barreiras-mastery-learning]].

O Seedlight vai alem do Mastery Learning original em um ponto critico: o threshold de dominio. Bloom usava criterio fixo (80-90%) por viabilidade operacional. O [[bkt-threshold-dinamico-por-grafo]] propoe threshold variavel conforme a centralidade do conceito no Knowledge Graph — conceitos estruturais com muitas dependencias exigem dominio mais alto, evitando a cadeia de [[esquemas-mentais]] mal formados que Piaget descreve (assimilacao defeituosa propagando em cascata).
