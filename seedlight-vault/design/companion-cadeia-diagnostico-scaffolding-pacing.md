---
seedlight-component: companion
status: hypothesis
based-on: ["[[esquemas-mentais]]", "[[two-sigma-problem]]"]
tags: [foundational, scaffolding, assessment]
---

# Companion — Cadeia Diagnostico → Scaffolding → Pacing

## Decisao / Hipotese

Os tres mecanismos do tutor (diagnostico continuo, scaffolding e pacing adaptativo) operam em cadeia com direcao causal definida:

1. **Diagnostico continuo** (sensor) — capta sinais: velocidade de resposta, hesitacao, tipo de erro (conceitual vs execucao), necessidade de dicas
2. **Scaffolding** (dosagem) — com base nos sinais, decide o nivel de suporte: mais andaime, menos andaime, ou manter. A retirada e gradual e calibrada
3. **Pacing adaptativo** (portao) — decide se a crianca avanca ou nao. Quando o scaffolding chega a zero e a crianca opera sozinha, o portao abre

A ordem importa: diagnostico alimenta scaffolding, scaffolding alimenta pacing. Nao o contrario.

Analogia: medico → dosagem do remedio → alta. O medico nao da alta e depois decide a dosagem. Ele observa, ajusta, e quando a dosagem chega a zero e o paciente esta bem, libera.

## Fundamentacao

O [[two-sigma-problem]] identifica diagnostico continuo, pacing adaptativo e feedback imediato como mecanismos do tutor, mas nao explicita a relacao entre eles. Vygotsky adiciona o conceito de scaffolding (retirada gradual de suporte) que conecta diagnostico a pacing. A nota [[companion-mecanismos-tutoria]] mapeia cada mecanismo para um componente, mas esta nota define *como* eles se comunicam.

O tipo de portao do pacing (checkpoint explicito vs inferencia fluida) e uma decisao separada explorada em [[companion-checkpoints-vs-inferencia]], mas o fluxo diagnostico → scaffolding → pacing e o mesmo independente do tipo de portao.

## Trade-offs

- A cadeia implica que o BKT (diagnostico + pacing) e o LLM (scaffolding via interacao) precisam de um protocolo de comunicacao claro — o orchestrator ganha papel central
- Scaffolding exige que o LLM module o nivel de ajuda de forma granular, nao binario (ajuda total vs nenhuma ajuda) — desafio para modelos pequenos
- A velocidade do ciclo importa: diagnostico → scaffolding → pacing deve ser continuo, nao em batches

## Status

Hipotese arquitetural. Define o fluxo de dados entre componentes. Validacao na Fase 3 (arquitetura do orchestrator).
