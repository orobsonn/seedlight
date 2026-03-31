---
seedlight-component: infra
status: hypothesis
based-on: ["[[ml-classico-ia-generativa]]"]
tags: #offline-first, #critical
---

# Reavaliar Premissas de Viabilidade Offline

## Decisao / Hipotese

As premissas de limitacao de hardware e modelos pequenos firmadas no inicio do projeto podem estar desatualizadas. A velocidade de evolucao da IA (2 anos ≈ 1 geracao inteira de capacidade) significa que restricoes que pareciam duras em 2024 podem ter amolecido significativamente.

A decisao "LLM no dispositivo desde o inicio (sem dependencia de internet)" deve ser validada com benchmarks reais na Area 5, nao mantida por inércia.

Cenarios possiveis que devem ser avaliados com dados concretos:
1. **Offline-only** — tudo roda no Pi 5 (premissa original)
2. **Offline-first** — funciona sem internet, mas sincroniza quando tem conexao
3. **Hibrido com degradacao graceful** — experiencia completa na nuvem, modo basico offline
4. **Cloud com cache agressivo** — modelo na nuvem, atividades pre-cacheadas pro offline

## Fundamentacao

A motivacao original (privacidade, acesso em areas sem internet, soberania dos dados) continua valida. A questao e se existe arquitetura que preserve esses valores sem ser puramente offline. A Area 5 (benchmarks no Pi 5) e o ponto de decisao baseado em evidencia.

## Trade-offs

- (+) Decisao informada por dados, nao por suposicao
- (+) Abre espaco pra arquiteturas mais flexiveis sem abandonar valores
- (-) Risco de scope creep — cloud "temporario" pode virar permanente
- (-) Cada cenario exige arquitetura diferente — decidir tarde custa mais

## Status

Hipotese. Decisao adiada para apos Area 5 (benchmarks reais no Pi 5). Nao mudar premissa antes de ter evidencia.
