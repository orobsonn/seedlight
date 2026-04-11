---
kind: technique
sources: []
seedlight-component: companion
tags: #foundational
---

# GRPO — RL Economico para LLMs

Group Relative Policy Optimization (GRPO) e o algoritmo de Reinforcement Learning usado pelo DeepSeek-R1, que elimina o value model do pipeline PPO classico, reduzindo ~30-40% o consumo de memoria.

## Como funciona

PPO classico precisa de 3 modelos simultaneos: modelo sendo treinado + reward model + value model. O value model estima "quao boa sera a proxima resposta" pra calcular a vantagem (advantage).

GRPO elimina o value model com uma solucao elegante: pra cada prompt, gera **N respostas** (tipicamente 4-8), avalia todas com o reward model, e usa a **media do grupo como baseline**. Respostas acima da media recebem reforco positivo, abaixo recebem negativo. A comparacao relativa dentro do grupo substitui a estimativa do value model.

## Implicacao pratica

Com 30-40% menos memoria, o pipeline SFT+RL de um modelo 1.5B com LoRA cabe numa unica RTX 4090 (24GB VRAM). Custo de treinamento em cloud (Vast.ai, RunPod): R$150-500 por run (24-72h de GPU). A diferenca entre acessivel e proibitivo.

## Por que importa para o Seedlight

GRPO viabiliza o [[companion-pipeline-slm-especializado]] com custo acessivel. Combinado com reward functions pedagogicas derivadas de [[zona-desenvolvimento-proximal]], [[tutoring-moves]] e [[motivacao-intrinseca-sdt]], permite treinar um tutor especializado sem infraestrutura de grande empresa. O fato de ser o mesmo algoritmo que ensinou o DeepSeek-R1 a raciocinar valida a abordagem — se GRPO ensinou raciocinio geral, pode ensinar tutoria educacional.
