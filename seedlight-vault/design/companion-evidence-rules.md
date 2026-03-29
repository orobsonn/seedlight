---
seedlight-component: companion
status: hypothesis
based-on: ["[[stealth-assessment]]", "[[evidence-centered-design]]", "[[triangulo-avaliacao]]"]
tags: [assessment, foundational]
---

# Companion — Evidence Rules como Tool

## Decisao / Hipotese

As evidence rules sao implementadas como uma **tool do Companion** que roda continuamente durante a interacao, traduzindo acoes da crianca em sinais diagnosticos (acerto/erro/parcial) que alimentam o BKT.

## Fundamentacao

O BKT classico espera input binario: acertou ou errou. Mas o Seedlight opera em interacao aberta — conversa, micromundo, construcao. A fronteira entre acerto e erro e ambigua:

- Crianca tentou 3 vezes antes de acertar — 2 erros e 1 acerto, ou 1 exploracao bem-sucedida?
- Crianca acertou mas nao consegue explicar por que — e acerto?
- Crianca pediu ajuda — conta como erro?
- Crianca usou conceito errado mas chegou no resultado certo — e acerto?

A tool de evidence rules resolve essa ambiguidade aplicando regras contextuais:

- **Tempo de resposta** — resposta rapida e confiante vs hesitante
- **Pedido de ajuda** — antes ou depois de tentar
- **Mudanca de estrategia** — indica metacognicao (positivo) ou confusao (depende do contexto)
- **Transferencia** — usou conceito em contexto novo (evidencia forte de dominio)
- **Explicacao** — consegue verbalizar o raciocinio (evidencia mais forte que acerto mecanico)

### Por que tool e nao componente separado

O Companion ja "ve" toda a interacao — ele e quem conversa com a crianca. Extrair evidence rules pra componente separado criaria acoplamento desnecessario e duplicacao de contexto. Como tool, as rules acessam o mesmo contexto da conversa e produzem output estruturado pro BKT.

Alinhado com filosofia Anthropic de composable patterns: tool simples, responsabilidade unica, composicao via orquestracao.

## Trade-offs

- **Complexidade das regras** — interacao aberta e inerentemente mais dificil de interpretar que prova. Regras simples demais perdem nuance; complexas demais sao frageis
- **LLM como interpretador** — um modelo de linguagem pode ser a propria evidence rule (interpretar interacao em linguagem natural). Mas isso adiciona latencia e imprevisibilidade. Trade-off entre interpretacao rica e determinismo
- **Calibracao** — as regras precisam ser calibradas pra nao gerar falsos positivos (crianca "sabe" mas nao sabe) nem falsos negativos (crianca sabe mas o sistema nao reconhece). Falsos negativos sao piores em contexto educacional — geram revisao desnecessaria e frustram

## Status

Hipotese. Formato especifico das rules (regras deterministicas vs LLM-based vs hibrido) sera explorado na Fase 2 (Area 2.2 — Knowledge Tracing) e Fase 3 (Area 4 — Arquitetura de Agentes).
