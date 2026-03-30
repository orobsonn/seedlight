---
seedlight-component: equity-layer
status: hypothesis
based-on: ["[[pipeline-bias-educacional]]", "[[armadilhas-de-abstracao]]"]
tags: [fairness, offline-first, critical]
---

# Equity Layer — Intervencao Proporcional

## Decisao / Hipotese

Estrategia de fairness viavel dentro das restricoes de hardware do Seedlight (Pi 5, 8GB RAM). Em vez de 4 camadas de auditoria em tempo real (inviavel e cairia na [[armadilhas-de-abstracao|Portability Trap]]), investimento diferenciado por etapa do [[pipeline-bias-educacional]]:

| Etapa | Estrategia | Custo computacional |
|-------|-----------|-------------------|
| 1 — Dados | **Investimento pesado**: validar que sensores medem a mesma coisa pra todos os grupos. Trabalho de design e calibracao, nao de computacao em tempo real | Pre-deploy |
| 3 — Decisao | **Auditoria batch**: checagens periodicas de distribuicao de oportunidades por grupo. Equity Layer roda em batch, nao a cada interacao | Baixo (periodico) |
| 2 e 4 | **Monitoramento passivo**: logs estruturados que permitem auditoria posterior | Minimo |

## Fundamentacao

O insight central e que **fairness nao precisa ser tempo real em todas as etapas**. A etapa 1 e a mais critica porque measurement bias e o combustivel do [[feedback-loop-bias]]. Se o dado entra limpo, as etapas seguintes tem muito menos com o que errar. Auditar so a saida (etapa 3) sem corrigir a entrada mascara o problema.

## Trade-offs

- **A favor**: cabe no hardware, foca recurso onde tem mais impacto, evita Portability Trap
- **Contra**: monitoramento passivo nas etapas 2/4 depende de alguem analisar os logs — quem faz isso num contexto sem suporte tecnico?
- **Risco**: calibracao pre-deploy assume que os grupos sao conhecidos de antemao. Novas populacoes nao previstas podem nao ser cobertas

## Status

Hipotese derivada de [[pipeline-bias-educacional]] (Kizilcec & Lee) e [[armadilhas-de-abstracao]] (Selbst). Validacao depende de prototipo funcional na Fase 6.
