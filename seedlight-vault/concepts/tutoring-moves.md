---
kind: technique
sources: ["[[graesser-2004-autotutor]]"]
seedlight-component: companion
tags: #scaffolding
---

# Tutoring Moves

## O que e

Repertorio de acoes dialogicas que um tutor usa para guiar o aluno sem dar a resposta diretamente. Identificadas por Graesser et al. (2004) no AutoTutor:

- **Pumping** — "me conta mais sobre isso" — puxa o aluno pra elaborar seu raciocinio
- **Hints** — "pensa no que acontece quando a agua esquenta..." — direciona sem revelar
- **Prompts** — "qual e a palavra pra quando a agua vira gas?" — pede informacao especifica
- **Assertions** — "isso mesmo, evaporacao" — confirma e nomeia o conceito

O AutoTutor de 2004 era limitado por NLP primitiva — nao entendia respostas inesperadas. LLMs resolvem esse gargalo: conseguem aplicar tutoring moves de forma natural em qualquer dominio.

A escolha de *qual* move usar nao deve ser do LLM — segue o padrao [[its-estrategista-executor]]. O harness decide o nivel de scaffolding e o tipo de move; o LLM executa via dialogo natural.

## Por que importa para o Seedlight

O Companion precisa de um vocabulario de acoes pedagogicas, nao apenas "conversar". Tutoring moves sao o mecanismo concreto pelo qual o LLM implementa [[zdp-scaffolding]] — dosando ajuda do pumping (menos suporte) ate assertions (mais suporte), controlado pelo harness com base no BKT e no [[engagement-detector-fairness]].
