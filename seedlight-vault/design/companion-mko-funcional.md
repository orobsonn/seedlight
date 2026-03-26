---
seedlight-component: companion
status: hypothesis
based-on: ["[[esquemas-mentais]]"]
tags: [longitudinal, motivation, open-question]
---

# Companion — MKO Funcional, Nao Substituto Humano

## Decisao / Hipotese

O Companion e um MKO (More Knowledgeable Other) funcional — sabe mais e opera na ZDP da crianca — mas nao substitui presenca humana. O vinculo que ele constroi e de natureza diferente: nao e presenca fisica, e **presenca cognitiva** construida por consistencia, personalizacao e longitudinalidade.

No MVP, o Companion e apenas chat. Isso nao e limitacao — texto pode criar presenca se:
- O Companion **lembra** (o cachorro da crianca, o que ela achou dificil, o que estudou semana passada)
- O Companion **e consistente** (mesma personalidade, mesmo tom, ao longo de meses)
- O Companion **conhece** o mundo da crianca (esquemas, interesses, contexto)

Avatar e interacao em tempo real sao evolucao futura, nao requisito do MVP.

## Fundamentacao

Vygotsky defende que aprendizagem e fundamentalmente social — acontece entre pessoas e depois e internalizada. O MKO (More Knowledgeable Other) e quem puxa a crianca dentro da ZDP. O Companion cumpre esse papel funcionalmente, mas sem a dimensao social completa que Vygotsky descrevia.

A nota [[engagement-vinculo-vs-coercao]] levanta que engajamento vem de vinculo, nao coercao. Este insight complementa: o vinculo do Companion nao e social no sentido humano, e cognitivo — a crianca internaliza o processo de pensar com o Companion, como uma crianca internaliza a voz da mae que lia com ela.

A decisao [[curriculum-esquema-antes-assunto]] reforça: o Companion que conhece o mundo da crianca ja esta construindo presenca cognitiva ao demonstrar que se importa com o contexto dela.

## Trade-offs

- Presenca cognitiva depende de memoria persistente de longo prazo — GraphRAG e central
- Risco de a crianca desenvolver dependencia do Companion em vez de internalizar o processo — scaffolding precisa incluir retirada gradual do proprio Companion
- A qualidade do vinculo depende da qualidade das respostas — modelos pequenos podem quebrar a ilusao de presenca com respostas genericas

## Status

Hipotese. Permeia o design do Companion como um todo. A questao "IA pode ser MKO de verdade?" permanece aberta — talvez nao importe se funciona na pratica.
