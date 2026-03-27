---
seedlight-component: companion
status: hypothesis
based-on: ["[[construcionismo]]", "[[esquemas-mentais]]", "[[zona-desenvolvimento-proximal]]"]
tags: [foundational, scaffolding]
---

# Companion — Arquiteto de Micromundos

## Decisao / Hipotese

O papel principal do Companion nao e ensinar (modelo CAI) nem apenas fazer scaffolding reativo (Vygotsky puro). O Companion e um **arquiteto de micromundos**: cria e adapta ambientes de exploracao baseados nos esquemas e interesses da crianca, onde ela constroi coisas significativas e esbarra em conceitos poderosos.

Dois papeis integrados:

1. **Arquiteto** — constroi/adapta micromundos alinhados com os esquemas da crianca, seguindo o principio [[curriculum-esquema-antes-assunto]]. O micromundo e projetado para que a crianca esbarre em situacoes que forcam acomodacao dos [[esquemas-mentais]] de forma segura e engajante
2. **MKO dentro do micromundo** — quando a crianca trava, faz scaffolding na [[zona-desenvolvimento-proximal]] para desbloquear, mas sem tirar o controle dela. O insight [[companion-verbalizacao-como-aprendizagem]] se aplica aqui: mesmo dentro do micromundo, quem verbaliza a conclusao e a crianca

Isso integra Piaget (acomodacao), Vygotsky (ZDP + scaffolding) e Papert ([[construcionismo]] — aprender construindo em ambientes ricos). O micromundo e a "maquina de acomodacao controlada" — um ambiente onde Piaget acontece por design, nao por acaso.

## Fundamentacao

Papert critica o modelo CAI em [[papert-1980-mindstorms]]: "the computer is being used to program the child. In my vision, the child programs the computer." Mas o Seedlight precisa de um MKO (Vygotsky) — a crianca nao pode ser solta sem suporte. A sintese e que o Companion atua primariamente no *ambiente* (construindo micromundos) e secundariamente na *interacao direta* (scaffolding quando necessario).

A cadeia [[companion-cadeia-diagnostico-scaffolding-pacing]] se mantem, mas ganha uma camada anterior: antes de diagnosticar e fazer scaffolding, o Companion precisa ter construido um micromundo adequado. O diagnostico continuo tambem alimenta a adaptacao do micromundo, nao apenas do scaffolding.

## Trade-offs

- O Companion como chat nao constitui um micromundo — o formato de interacao do Seedlight precisa evoluir alem de chat puro para suportar construcao ativa pela crianca
- Criar micromundos dinamicamente exige capacidades generativas do LLM que podem estar alem de modelos de 1-3B — tensao com a restricao on-device
- A questao "o que a crianca constroi no Seedlight?" permanece aberta — sem resposta pra isso, o conceito de micromundo fica teorico
- Risco de over-engineering: nem toda interacao precisa ser um micromundo. Conversa, historias, perguntas simples tambem sao caminhos validos de aprendizagem

## Status

Hipotese arquitetural. Redefine o papel do Companion de "tutor" para "arquiteto + tutor". Validacao depende de resolver a questao de formato (alem de chat) e da capacidade de modelos pequenos gerarem ambientes de exploracao.
