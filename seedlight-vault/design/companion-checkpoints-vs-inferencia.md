---
seedlight-component: companion
status: hypothesis
based-on: ["[[two-sigma-problem]]"]
tags: [scaffolding, assessment, open-question]
---

# Companion — Checkpoints Explicitos vs Inferencia Fluida

## Decisao / Hipotese

O Seedlight precisa decidir entre duas estrategias para implementar pacing adaptativo:

1. **Checkpoints explicitos** (estilo mastery learning) — o sistema apresenta verificacoes estruturadas antes de avancar. Mais proximo do que Bloom testou em grupo (1 sigma). Mais facil de implementar, mais previsivel, mas pode parecer "prova disfarçada"
2. **Inferencia fluida** (estilo tutor humano) — o sistema tenta perceber organicamente se o aluno entendeu, sem parar para testar. Mais proximo dos 2 sigma, mas tecnicamente muito mais dificil com um modelo pequeno rodando no dispositivo

A tensao real e: mastery learning em grupo (checkpoints) ja da 1 sigma. Tentar inferencia fluida busca os 2 sigma, mas com risco de falhar e entregar menos que 1.

## Fundamentacao

O [[two-sigma-problem]] mostra que mastery learning em grupo — mesma sala de 30 alunos mas com checkpoints de dominio — ja produz 1 sigma de ganho. Isso significa que metade do efeito do tutor vem so de respeitar o ritmo do aluno, independente de como voce detecta o dominio. A nota [[companion-mecanismos-tutoria]] mapeia pacing adaptativo para o BKT, mas a questao aqui e anterior: qual o *mecanismo de verificacao* que alimenta o BKT?

## Trade-offs

- Checkpoints explicitos sao mais seguros e viaveis no MVP, mas podem quebrar engajamento
- Inferencia fluida e o ideal mas depende de capacidade do modelo que talvez nao exista em 1-3B
- Uma abordagem hibrida (inferencia quando possivel, checkpoint quando necessario) pode ser o caminho, mas adiciona complexidade ao orchestrator

## Status

Hipotese. Decisao depende de validacao tecnica na Fase 2 (capacidade real dos modelos pequenos) e Fase 3 (arquitetura do orchestrator).
