---
kind: pattern
sources: ["[[vanlehn-2011-its-effectiveness]]", "[[koedinger-2007-cognitive-tutors]]", "[[graesser-2004-autotutor]]"]
seedlight-component: companion, bkt, orchestrator
tags: #scaffolding, #foundational
---

# ITS: Separacao Estrategista-Executor

## O que e

Padrao arquitetural derivado de 30 anos de pesquisa em Intelligent Tutoring Systems: a **estrategia pedagogica** (quando dar dica, quando deixar errar, quando mudar de assunto) deve ser decidida por componentes especializados (BKT + regras + engagement detector), nao pelo motor de dialogo.

Nos ITS classicos, o model tracing + knowledge tracing decidiam a estrategia e a interface executava. No Seedlight, o principio se mantém: o **harness e o estrategista**, o **LLM e o executor**.

O LLM recebe instrucoes do harness sobre nivel de scaffolding, tipo de tutoring move (pumping, hints, prompts, assertions), e se deve permitir Productive Failure ou intervir. O LLM entao *executa* essa estrategia via dialogo natural — algo que os ITS classicos nao conseguiam fazer bem por limitacoes de NLP.

Essa separacao resolve dois problemas simultaneamente:

1. O vicio do LLM de **dar respostas** em vez de ensinar — o harness controla quando o LLM pode revelar informacao, alinhando com [[productive-failure]] e [[zdp-scaffolding]]
2. A limitacao dos ITS classicos a **dominios fechados** — o LLM faz "model tracing" via compreensao de linguagem natural, funcionando em qualquer dominio (matematica, historia, ciencias)

## Por que importa para o Seedlight

Este padrao e a espinha dorsal da arquitetura do Companion. Sem ele, o LLM tende a ser um "respondedor" em vez de um tutor. A pesquisa de VanLehn (2011) mostrou que ITS atingem d=0.76 vs d=0.79 da tutoria humana — mas apenas com feedback step-level. O Companion so atinge esse nivel se o harness orquestrar a estrategia e o LLM executar com granularidade de passo, nao de resposta final.

Conecta diretamente com [[autonomia-proporcional-confianca]] — o nivel de scaffolding que o harness injeta no LLM deve ser proporcional a confianca do BKT no dominio do aluno.
