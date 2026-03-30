---
seedlight-component: companion, orchestrator
status: hypothesis
based-on: ["[[autonomia-proporcional-confianca]]", "[[allocation-bias-prevalente]]"]
tags: [fairness, scaffolding, offline-first]
---

# Companion — Fallback com Humano no Loop

## Decisao / Hipotese

O Companion opera com tres camadas de fallback, degradando com graca conforme disponibilidade de suporte humano:

1. **Humano presente** (pai, professor, voluntario) → Companion informa, humano decide. Ideal pra decisoes de alta consequencia com confianca baixa
2. **Humano remoto** (professor voluntario via rede) → viavel com conectividade intermitente. Companion acumula sinais e escala quando houver conexao
3. **Sem humano** → Companion adota [[companion-postura-conservadora]]. Na duvida, nao reduz complexidade

## Fundamentacao

Baker & Hawn (2021) documentam que sistemas educacionais que funcionaram tinham humano interpretando sinais no contexto — distinguindo estado temporario de capacidade ([[companion-estado-vs-capacidade]]). Mas o Seedlight atende justamente quem nao tem acesso a esse humano ([[armadilhas-de-abstracao|Portability Trap]]). O design de fallback resolve a tensao: tenta humano quando possivel, mas nao quebra sem ele.

## Trade-offs

- **A favor**: design resiliente, funciona em qualquer contexto, escala naturalmente
- **Contra**: camada 2 (humano remoto) depende de infraestrutura de voluntariado que nao existe ainda
- **Contra**: camada 3 (sem humano) e a que mais precisa funcionar bem e a que tem menos supervisao
- **Duvida aberta**: como atrair e manter professores voluntarios? Modelo sustentavel?

## Status

Hipotese. Camadas 1 e 3 sao de design tecnico (Fase 3+). Camada 2 depende de decisoes operacionais e parcerias.
