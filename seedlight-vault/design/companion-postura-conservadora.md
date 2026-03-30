---
seedlight-component: companion, bkt
status: hypothesis
based-on: ["[[autonomia-proporcional-confianca]]", "[[feedback-loop-bias]]", "[[equity-layer-fairness-metric]]"]
tags: [fairness, critical]
---

# Companion — Postura Conservadora

## Decisao / Hipotese

Quando a confianca do modelo e baixa e nao ha humano disponivel, o Companion adota postura conservadora: **na duvida, nao reduz complexidade. Mantem o nivel e adapta o formato.**

### Justificativa assimetrica

O custo de **subestimar** (reduzir complexidade indevidamente) e maior que o custo de **superestimar** (manter complexidade quando a crianca esta com dificuldade):

- **Subestimar** → alimenta [[feedback-loop-bias]], viola [[equity-layer-fairness-metric|equal opportunity]], destroi competencia e autonomia ([[motivacao-intrinseca-sdt|SDT]]), dano acumulado longitudinalmente
- **Superestimar** → crianca encontra dificuldade, pede ajuda ou demonstra frustração, scaffolding entra naturalmente, engagement detector detecta e ajusta

A assimetria e clara: subestimar causa dano silencioso e cumulativo; superestimar gera sinal visivel que o sistema pode corrigir.

### Na pratica

- Adaptar **formato** (visual, textual, interativo, duracao) sem reduzir nivel cognitivo
- Adaptar **scaffolding** (mais dicas, decomposicao do problema) sem eliminar o desafio
- Se engajamento cai apos N tentativas com scaffolding, ai sim considerar reducao — mas com flag pra auditoria

## Trade-offs

- **A favor**: protege contra o bias mais perigoso (subestimacao silenciosa), alinhado com equal opportunity
- **Contra**: pode gerar frustracao em criancas que realmente precisam de nivel mais baixo temporariamente
- **Mitigacao**: [[companion-estado-vs-capacidade]] — se o sistema aprende a distinguir estado de capacidade, a postura conservadora e necessaria com menos frequencia

## Status

Hipotese. Depende de calibracao do threshold de confianca (Fase 5+) e validacao com criancas reais (Fase 6).
