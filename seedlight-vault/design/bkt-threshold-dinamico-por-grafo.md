---
seedlight-component: bkt
status: hypothesis
based-on: ["[[two-sigma-problem]]", "[[construcionismo]]"]
tags: [foundational, assessment]
---

# BKT — Threshold Dinamico por Centralidade no Grafo

## Decisao / Hipotese

O nivel de dominio exigido para avancar nao deve ser um threshold fixo (como os 80-90% do Mastery Learning de Bloom). Deve variar conforme a **centralidade do conceito no Knowledge Graph**.

A regra: quanto mais dependencias de saida um no tem, mais estrutural ele e — e mais alto o threshold de dominio exigido. Nos folha (perifericos, sem dependentes) aceitam threshold menor.

Isso resolve uma limitacao do Mastery Learning original: Bloom usava threshold fixo porque era operacionalmente viavel em sala de aula. O Seedlight pode calcular dinamicamente porque o [[graphrag-powerful-ideas-como-nos|Knowledge Graph organizado por powerful ideas]] ja carrega a informacao de dependencia estrutural — nos centrais (powerful ideas) naturalmente tem mais arestas de saida.

## Fundamentacao

O [[two-sigma-problem]] identifica pacing adaptativo como mecanismo critico do tutor, e o Mastery Learning (Bloom 1968) formalizou a ideia de que dominio deve preceder avanco. Mas o threshold fixo e um compromisso pratico, nao um principio pedagogico. A teoria de [[esquemas-mentais]] de Piaget mostra por que: um esquema mal formado gera assimilacao defeituosa em cadeia — cada camada amplifica o erro. Isso significa que o custo de um falso positivo (achar que dominou quando nao dominou) escala com a centralidade do conceito.

A [[companion-cadeia-diagnostico-scaffolding-pacing]] define o pacing como "portao" no fluxo. Esta nota refina o criterio desse portao: nao e um valor fixo, e uma funcao da posicao no grafo.

## Trade-offs

- Exige que o Knowledge Graph tenha arestas de dependencia explicitas e bem curadas — erro na modelagem do grafo propaga para o pacing
- Calcular centralidade em tempo real no dispositivo pode ter custo computacional — mas grafos educacionais tendem a ser pequenos o suficiente
- O threshold minimo precisa de um piso (nao pode ser zero pra nos folha) — definir esse piso e uma decisao de calibracao empirica
- Risco de over-engineering: complicar o pacing alem do necessario antes de validar se threshold fixo ja nao resolve a maioria dos casos

## Status

Hipotese. Depende do design do Knowledge Graph (Fase 3) e da implementacao do BKT (Fase 2) para validacao. Possivel abordagem: comecar com threshold fixo e evoluir para dinamico se os dados mostrarem necessidade.
