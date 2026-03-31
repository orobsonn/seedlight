---
seedlight-component: companion
status: hypothesis
based-on: ["[[its-estrategista-executor]]", "[[ml-classico-ia-generativa]]"]
tags: #future
---

# Pipeline SLM Especializado: Distillation + SFT + RL

## Decisao / Hipotese

Treinar um SLM (1.5B) especializado em tutoria educacional usando pipeline de 3 etapas:

1. **Distillation** — usar LLM grande pra gerar dialogos educacionais sinteticos (tutor-aluno) como dataset de treinamento
2. **SFT (Supervised Fine-Tuning)** — fine-tunar modelo base (Qwen 1.5B ou similar) nesses dialogos
3. **RL (GRPO)** — refinar com reinforcement learning usando reward functions pedagogicas (compreensao, nivel adequado, motivacao)

Pipeline validado em outros dominios: DeepSeek-R1 usou distillation pra treinar versoes menores, DeepResearcher treinou 7B com GRPO via veRL. Viavel em 1x RTX 4090 com LoRA.

## Fundamentacao

Um modelo generico de 1.5B e razoavel. Um modelo de 1.5B treinado especificamente pra tutoria educacional pode ser extraordinario pro seu tamanho — porque nao precisa saber tudo, so precisa ser excepcional em ensinar conceitos de ensino fundamental.

## Trade-offs

- (+) Modelo menor e mais rapido no dispositivo, liberando RAM pra outros componentes
- (+) Comportamento de tutor embutido no modelo, menos dependencia de prompt engineering
- (+) GRPO sem value model economiza ~30-40% memoria vs PPO
- (-) Dados sinteticos podem nao refletir interacoes reais de criancas brasileiras (Baker & Hawn, Portability Trap de Selbst)
- (-) Precisa de validacao com dados reais apos deploy

## Status

Hipotese. Depende de: (1) benchmarks de modelos base no Pi 5 (Area 5.2), (2) estudo de GRPO/veRL (Area 5.3), (3) dados reais pra validacao (Fase 6). Alerta: validar especificamente com criancas da populacao-alvo, nao apenas metricas de benchmark.
