---
seedlight-component: companion
status: hypothesis
based-on: ["[[esquemas-mentais]]"]
tags: [foundational, scaffolding, assessment]
---

# Companion — Estagios Cognitivos como Calibracao

## Decisao / Hipotese

O Companion deve adaptar nao apenas o conteudo, mas o **tipo de raciocinio** que exige da crianca, baseado nos estagios de desenvolvimento cognitivo de Piaget:

| Estagio | Idade aprox. | Implicacao pro Companion |
|---------|-------------|--------------------------|
| Sensorio-motor | 0-2 | Fora do escopo inicial |
| Pre-operatorio | 2-7 | Simbolos, historias, sem logica formal |
| Operatorio concreto | 7-11 | Logica com objetos concretos, exemplos tangiveis, manipulacao |
| Operatorio formal | 12+ | Abstraçao, hipoteses, pensamento formal |

A idade (coletada no onboarding via formulario basico com nome e data de nascimento) serve como **default inicial**, mas o diagnostico continuo refina o estagio real por area de conhecimento. Uma crianca de 10 anos pode estar no operatorio formal em xadrez e no pre-operatorio em raciocinio social — o Companion precisa tratar cada dominio independentemente.

Isso significa que o estagio nao e um atributo global da crianca, mas um **mapa por dominio** que evolui com o tempo.

## Fundamentacao

Os [[esquemas-mentais]] de Piaget mostram que a idade muda qualitativamente o tipo de raciocinio, nao so a quantidade. Uma crianca de 8 anos nao consegue pensar em abstracao — nao por falta de inteligencia, mas porque o hardware cognitivo ainda nao suporta. Ensinar algebra como conceito abstrato nesse estagio falha nao por problema de metodo, mas por incompatibilidade cognitiva.

O [[two-sigma-problem]] identifica diagnostico continuo como mecanismo do tutor — aqui ele ganha uma dimensao extra: alem de diagnosticar *o que* a crianca sabe, o Companion precisa diagnosticar *como* ela pensa (concreto vs abstrato) em cada dominio.

A nota [[companion-mecanismos-tutoria]] mapeia diagnostico para BKT + analise de padroes. O estagio cognitivo adiciona uma camada: o BKT mede dominio de conteudo, mas o estagio determina *como* apresentar esse conteudo.

## Trade-offs

- Mapear estagio por dominio e mais complexo que um estagio global, mas evita subestimar ou superestimar a crianca
- Requer que o modelo de learner profile tenha granularidade por dominio, nao so por aluno
- A calibracao automatica de estagio depende de sinais comportamentais que um modelo pequeno pode ter dificuldade de captar — tensao com a restricao de hardware

## Status

Hipotese fundamental. Permeia toda a interacao do Companion. Validacao depende da capacidade real dos modelos pequenos de distinguir tipos de raciocinio (Fase 2).
