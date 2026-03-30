---
kind: principle
sources: ["[[baker-hawn-2021-algorithmic-bias-education]]"]
seedlight-component: companion, orchestrator
tags: [fairness, scaffolding]
---

# Autonomia Proporcional a Confianca

## O que e

Principio derivado de Baker & Hawn (2021): o nivel de autonomia que um sistema educacional adaptativo deve ter e proporcional a confianca do modelo nas suas inferencias.

- **Alta confianca** (BKT estavel, engagement claro, padrao consistente) → sistema age sozinho
- **Baixa confianca** (sinais contraditorios, mudanca brusca de comportamento, contexto novo) → escala pra humano se disponivel, ou adota postura conservadora se nao

Nos casos documentados por Baker & Hawn, sistemas que respeitaram esse principio (informando humanos em vez de decidir sozinhos) tiveram resultados positivos. Sistemas que tomavam decisoes autonomas com confianca baixa amplificavam bias.

## Por que importa para o Seedlight

O Companion opera como tutor autonomo, muitas vezes sem humano disponivel. Esse principio define quando o Companion pode agir e quando deve ser cauteloso. Conecta com [[companion-fallback-humano]] (tres camadas de degradacao) e [[companion-postura-conservadora]] (o que fazer quando confianca e baixa e nao tem humano). Tambem informa o design do orchestrator — ele precisa de um sinal de confianca agregado dos componentes pra decidir o nivel de autonomia em cada momento.
