---
seedlight-component: infra
status: hypothesis
based-on: ["[[knowledge-tracing-evolucao]]", "[[bkt-graphrag-complementaridade]]"]
tags: #offline-first, #critical
---

# Smartphone Android como Plataforma Primaria

## Decisao / Hipotese

Trocar o Raspberry Pi 5 como plataforma de referencia por smartphones Android mid-range que a familia ja possui. Um aparelho com Snapdragon 695 (faixa de R$1000 em 2025) roda modelos 3B em Q4_K_M a 10-15 tok/s — melhor que o Pi 5 (~8-12 tok/s para 3B) — gracas a NPU dedicada, GPU com backend Vulkan, e memoria LPDDR5 com mais bandwidth.

A licao do [[khanmigo-curriculo-fixo]] e do Kolibri (Area 8) e a mesma: ir onde o hardware ja esta. Nao exigir que a familia compre um dispositivo dedicado remove a maior barreira de adocao.

## Fundamentacao

A conta de quantizacao mostra que o range 1-3B em Q4_K_M cabe confortavelmente em 6-8GB de RAM (padrao em smartphones mid-range), com margem para BKT, GraphRAG e outros servicos conforme o design de [[bkt-graphrag-complementaridade]]. O gargalo no Pi 5 era bandwidth de memoria (~34 GB/s LPDDR4X) — smartphones com LPDDR5 chegam a 51 GB/s, e a NPU abre caminho alternativo de inferencia que o Pi 5 nao tem.

Isso conecta diretamente com [[infra-reavaliar-premissas-offline]]: o cenario "offline-first" fica mais viavel em smartphone porque o dispositivo ja tem conectividade intermitente (WiFi, dados moveis), permitindo sincronizacao oportunista sem depender de infraestrutura extra.

O [[companion-pipeline-slm-especializado]] (distillation + SFT + RL para 1.5B) ganha mais sentido nesse contexto: um modelo de 1.5B especializado roda a ~15-20 tok/s no smartphone, experiencia fluida, liberando RAM para os outros componentes da stack.

## Trade-offs

- (+) Barreira de adocao drasticamente reduzida — sem custo de hardware adicional
- (+) Hardware mais capaz que Pi 5 para inferencia (NPU, GPU Vulkan, LPDDR5)
- (+) Valida range 1-3B com margem confortavel, relaxa pressao de otimizacao extrema
- (+) Conectividade intermitente ja disponivel para sync oportunista
- (-) Fragmentacao Android — diversidade de SoCs, versoes de OS, disponibilidade de RAM real
- (-) Competicao por recursos com outros apps do usuario
- (-) Controle de ambiente mais limitado que hardware dedicado (termica, processos de fundo)
- (-) Pi 5 continua valido como plataforma de dev/benchmark — decisao e sobre deploy, nao sobre dev

## Status

Hipotese. Pi 5 permanece como plataforma de desenvolvimento e benchmark (controlada, reprodutivel). Smartphone Android e o alvo de deploy. Validacao concreta na Area 5.2 (benchmarks em dispositivos reais).
