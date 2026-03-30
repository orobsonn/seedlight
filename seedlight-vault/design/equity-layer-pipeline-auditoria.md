---
seedlight-component: equity-layer
status: hypothesis
based-on: ["[[aequitas-contexto-assistivo]]", "[[model-cards]]", "[[datasheets-for-datasets]]"]
tags: [fairness, critical]
---

# Equity Layer — Pipeline de Auditoria

## Decisao / Hipotese

Pipeline de ferramentas para auditoria de fairness no Seedlight, ordenado por prioridade:

| Ordem | Ferramenta | Papel | Quando usar |
|-------|-----------|-------|-------------|
| 1 | **Aequitas** | Framework de auditoria | Primeiro — define metricas a partir do contexto assistivo |
| 2 | **Fairlearn** | Mitigacao | Quando auditoria detectar disparidade — algoritmos de correcao |
| 3 | **AIF360** | Referencia complementar | Quando precisar de metrica ou algoritmo especifico que as outras nao tem |

### Como se integra com a estrategia existente

- [[equity-layer-intervencao-proporcional]] define **onde** auditar (etapa 1 pesado, etapa 3 batch)
- Este pipeline define **com que** auditar (Aequitas → Fairlearn → AIF360)
- [[model-cards]] e [[datasheets-for-datasets]] definem **como documentar** o que foi auditado

## Fundamentacao

Aequitas como ponto de entrada porque parte do contexto de uso ([[aequitas-contexto-assistivo]]), nao de metricas abstratas. Fairlearn para mitigacao ativa. AIF360 como biblioteca de referencia quando as outras nao cobrirem um caso especifico.

## Trade-offs

- **A favor**: pipeline claro com papel definido pra cada ferramenta, evita Formalism Trap (nao comeca pela metrica, comeca pelo contexto)
- **Contra**: todas sao ferramentas Python que assumem ambiente cloud/servidor. Precisam ser adaptadas pro contexto offline do Pi 5
- **Contra**: auditoria so funciona com dados reais — ate Fase 6, auditoria sera baseada em dados sinteticos ou simulados

## Status

Hipotese. Implementacao na Fase 5/6 quando houver modelos e dados reais pra auditar.
