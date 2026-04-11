---
kind: technique
sources: ["[[google-2026-turboquant]]"]
seedlight-component: infra
tags: #on-device, #foundational
---

# Quantizacao como Trade-off Multi-dimensional

Quantizacao reduz a precisao numerica dos pesos de um modelo (de 16 bits pra 4, 3, ou menos), permitindo rodar modelos em hardware limitado. Mas o impacto nao e uniforme — tarefas de raciocinio complexo sofrem desproporcionalmente mais que tarefas simples.

## Niveis e impacto

- **Q8 (8 bits):** perda < 1%, imperceptivel na pratica
- **Q5/Q6:** perda pequena, raciocinio multi-step comeca a ser afetado
- **Q4 (4 bits):** sweet spot — 2-5% de perda, mas desproporcional em raciocinio longo
- **Q2/Q3:** degradacao severa, alucinacao aumenta

O formato **k-quant** (Q4_K_M, Q5_K_M) agrupa pesos e usa precisao variavel por grupo, mitigando parte da perda. O sufixo S/M/L indica agressividade da compressao.

## Tecnicas de mitigacao

**Importance Matrix (imatrix)** mede estatisticamente quais pesos impactam mais o output e preserva esses com mais bits. **AWQ** faz o mesmo olhando pra ativacoes (valores intermediarios) em vez dos pesos diretamente. Ambas podem ser combinadas.

A implicacao direta pro [[companion-pipeline-slm-especializado]] e que o imatrix pode ser calibrado com dialogos educacionais — os pesos criticos pra tutoria ficam preservados enquanto pesos irrelevantes pro dominio sao comprimidos mais agressivamente.

O [[google-2026-turboquant]] leva isso ao extremo com quantizacao mista por camada (2-3 bits efetivos com qualidade de Q4), mas a conclusao pro Seedlight e que modelo pequeno especializado via SFT+RL supera modelo maior comprimido.

## Por que importa para o Seedlight

O pipeline de distribuicao fica: treinar em GPU cloud → quantizar com imatrix educacional → exportar como GGUF (arquivo unico com pesos + tokenizer + metadados) → rodar via llama.cpp no dispositivo. O formato GGUF suporta mmap, permitindo que o SO gerencie memoria dinamicamente — critico em smartphone onde outros apps competem por RAM.
