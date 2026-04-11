---
kind: constraint
sources: []
seedlight-component: infra
tags: #on-device, #critical
---

# Memory Bandwidth como Gargalo Real

Em inferencia de LLMs no dispositivo, o limite pratico nao e quanta RAM o modelo ocupa, mas quanta **bandwidth de memoria** o hardware oferece. A cada token gerado, o modelo precisa ler todos os pesos da memoria uma vez. Isso define o teto de tokens por segundo.

## A conta

- Pi 5 (LPDDR4X): ~34 GB/s de bandwidth
- Modelo 3B em Q4_K_M (~2GB): 34/2 = ~17 tok/s teorico, ~8-12 real
- Modelo 7B em Q4_K_M (~4.5GB): 34/4.5 = ~7.5 tok/s teorico, ~3-5 real

Smartphones com LPDDR5 chegam a ~51 GB/s, o que e uma das razoes pelas quais a [[infra-smartphone-como-plataforma]] performa melhor que o Pi 5 pra inferencia. NPUs dedicadas em SoCs modernos abrem caminho alternativo que nao depende da bandwidth de memoria principal.

## O KV cache agrava

Alem dos pesos, a inferencia precisa de RAM adicional pro KV cache (contexto da conversa). Um modelo 7B com contexto de 2048 tokens consome 500MB-1GB de KV cache em FP16. Isso reduz a RAM disponivel pros pesos e derruba o teto pratico de tamanho de modelo.

## Por que importa para o Seedlight

Bandwidth e o que torna o range 1-3B o limite pratico, nao 7B (que "cabe" na RAM mas roda lento demais). Uma conversa fluida com a crianca precisa de 8-10+ tok/s — abaixo disso o engajamento cai. Isso reforca a estrategia de modelo pequeno especializado: um 1.5B a 15-20 tok/s entrega experiencia melhor que um 7B a 4 tok/s, independente da qualidade do modelo maior.
