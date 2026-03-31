---
seedlight-component: companion, bkt, orchestrator
status: hypothesis
based-on: ["[[its-estrategista-executor]]", "[[step-level-feedback]]", "[[tutoring-moves]]"]
tags: #scaffolding, #foundational
---

# Companion: Harness como Estrategista Pedagogico

## Decisao / Hipotese

O LLM do Companion e o **executor** da estrategia pedagogica, nao o **decisor**. O harness (orquestrador) decide:

1. **Nivel de scaffolding** — alto/medio/baixo/zero — baseado no BKT (dominio do conceito) e engagement detector (frustacao produtiva vs improdutiva)
2. **Tipo de tutoring move** — pumping, hints, prompts, assertions — injetado como instrucao no prompt do LLM
3. **Quando permitir Productive Failure** — baseado em [[productive-failure]] e [[autonomia-proporcional-confianca]]
4. **Quando mudar de assunto** — baseado no BKT (dominio atingido ou frustacao improdutiva detectada)

O LLM recebe essas instrucoes e executa via dialogo natural com feedback step-level.

## Fundamentacao

30 anos de pesquisa em ITS mostram que a eficacia vem da orquestracao, nao do motor de dialogo. VanLehn (2011): step-level feedback e o diferenciador (d=0.76 vs d=0.31). Koedinger (2007): separacao model tracing/interface foi a chave do Cognitive Tutor. Graesser (2004): tutoring moves sao o mecanismo concreto de scaffolding.

O LLM resolve o gargalo historico (NLP primitiva, dominios fechados) mas introduz um novo risco: tendencia a dar respostas. O harness controla esse vicio.

## Trade-offs

- (+) LLM funciona em dominios abertos (historia, ciencias, nao so matematica)
- (+) BKT garante tracking preciso e interpretavel mesmo com LLM impreciso
- (+) Separacao permite trocar o LLM sem mudar a logica pedagogica
- (-) Latencia: harness precisa processar antes do LLM responder
- (-) Complexidade: orquestrar BKT + engagement + regras + LLM no Pi 5
- (-) Risco de o LLM ignorar instrucoes do harness (alignment do modelo pequeno)

## Status

Hipotese. Validacao depende de: (1) benchmarks do LLM no Pi 5 (Area 5), (2) estudo aprofundado de BKT (Area 2.2), (3) prototipo funcional (Fase 6).
