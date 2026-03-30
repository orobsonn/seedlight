---
kind: lesson
sources: ["[[baker-hawn-2021-algorithmic-bias-education]]"]
seedlight-component: equity-layer
tags: [fairness, foundational]
---

# Allocation Bias e Mais Prevalente que Measurement Bias

## O que e

Licao empirica de Baker & Hawn (2021): nos casos documentados de IA educacional, a maioria das falhas esta na etapa 3 do [[pipeline-bias-educacional]] (allocation bias — decisao desigual), nao na etapa 1 (measurement bias). Historical bias e mais comum que representational bias nos sistemas reais.

Isso surpreende porque a intuicao e que o problema comeca nos dados. Na pratica, muitos sistemas nem chegam a ter problemas sofisticados de measurement — a decisao ja e grosseiramente enviesada. Exemplos: course recommendation que sugere cursos faceis por perfil demografico, early warning que sinaliza alunos por CEP.

## Por que importa para o Seedlight

Nao contradiz a estrategia de [[equity-layer-intervencao-proporcional]] (investir pesado na etapa 1), mas adiciona um alerta: **mesmo com dados limpos, a logica de decisao do Companion pode introduzir bias proprio**. A auditoria batch na etapa 3 nao e opcional — e onde a maioria dos sistemas reais falhou. O Seedlight precisa auditar periodicamente a distribuicao de oportunidades de complexidade por grupo.
