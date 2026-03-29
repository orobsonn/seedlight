---
seedlight-component: bkt, companion
status: hypothesis
based-on: ["[[productive-failure]]", "[[mastery-learning]]"]
tags: [scaffolding, assessment]
---

# BKT como Decisor do Tipo de Instrucao

## Decisao / Hipotese

O BKT nao serve apenas para pacing (quando avancar), mas tambem para decidir o **tipo de instrucao** adequado para cada momento:

- **Alta probabilidade de dominio** do conceito-base → provavelmente assimilacao (encaixar no esquema existente) → instrucao direta e adequada
- **Baixa probabilidade ou desconhecido** → provavelmente acomodacao (precisa de esquema novo) → [[productive-failure]] e a abordagem correta — deixar a crianca tentar antes de ensinar

Isso transforma o BKT de um portao binario (avanca/nao avanca) em um **seletor de estrategia pedagogica**.

## Fundamentacao

O [[mastery-learning]] de Bloom usa avaliacao formativa para decidir pacing. Mas Kapur ([[productive-failure]]) mostra que a *forma* de ensinar importa tanto quanto o *quando*. O BKT tem a informacao necessaria para fazer essa distincao: se o modelo do aluno indica que os conceitos-base estao dominados, o novo conceito provavelmente e extensao (assimilacao). Se os conceitos-base estao frageis, o terreno cognitivo precisa ser preparado — e o fracasso produtivo e o mecanismo mais eficaz para isso.

Isso refina a [[companion-cadeia-diagnostico-scaffolding-pacing]]: o diagnostico (BKT) nao apenas alimenta o nivel de scaffolding, mas tambem seleciona a *estrategia* de scaffolding. E complementa o [[companion-productive-failure]]: o engagement detector decide *durante* a tentativa; o BKT decide *antes* se a tentativa deve acontecer.

## Trade-offs

- Requer que o grafo de pre-requisitos entre conceitos seja bem definido — o BKT precisa saber quais conceitos-base informam o conceito novo
- A distincao assimilacao/acomodacao e probabilistica, nao deterministica — o BKT pode errar, e o engagement detector serve como correcao em tempo real
- Adiciona complexidade ao orchestrator: alem de decidir "o que ensinar" e "quando avancar", precisa decidir "como ensinar"

## Status

Hipotese. Expande o papel do BKT de pacing para selecao de estrategia. Validacao depende da implementacao do BKT (Fase 2) e do grafo de conceitos (Fase 3).
