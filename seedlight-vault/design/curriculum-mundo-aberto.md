---
seedlight-component: curriculum
status: hypothesis
based-on: ["[[construcionismo]]", "[[esquemas-mentais]]", "[[zona-desenvolvimento-proximal]]"]
tags: [foundational, scaffolding]
---

# Curriculum — Mundo Aberto com Multiplas Portas de Entrada

## Decisao / Hipotese

O Curriculum Engine nao opera como uma sequencia linear de disciplinas e pre-requisitos (modelo escolar). Opera como um **mundo aberto** onde diferentes caminhos levam aos mesmos conceitos fundamentais. Cada crianca entra por uma porta diferente e percorre uma sequencia diferente de micromundos progressivos.

O ponto de entrada e determinado pela convergencia de tres diagnosticos:
- **Esquemas existentes** (Piaget) — o que a crianca ja sabe e como organiza esse conhecimento
- **ZDP** (Vygotsky) — o que ela quase consegue fazer com ajuda
- **Interesse** (Papert) — o que ela quer construir

O destino e compartilhado (fundamentos universais), mas o caminho e personalizado. Isso resolve a tensao entre Emergent Curriculum (curriculo emerge da crianca) e cobertura curricular (todos precisam aprender os mesmos fundamentos).

Analogia: um mundo aberto como Zelda — voce pode ir pra qualquer lugar, mas certos desafios naturalmente te preparam pra outros. O Curriculum Engine e o designer desse mundo, e o Companion e o guia dentro dele.

## Fundamentacao

O [[construcionismo]] de Papert introduz o conceito de microworlds progressivos: sequencias de ambientes onde cada um constroi sobre o anterior com pre-requisitos embutidos na experiencia (Geometry Turtle → Velocity Turtle → Acceleration Turtle → Newtonian Turtle). Isso elimina a cadeia de pre-requisitos explicitos da escola tradicional.

O principio [[curriculum-esquema-antes-assunto]] define que a direcao e esquema → assunto. Este insight estende: o *caminho inteiro* emerge dos esquemas, nao apenas a porta de entrada. E o [[curriculum-contexto-local-vem-da-crianca]] garante que o material das pontes vem da propria crianca.

A nota [[companion-arquiteto-de-micromundos]] define o Companion como construtor de ambientes. Aqui, o Curriculum Engine define **quais** micromundos construir e em **que sequencia**, baseado no perfil da crianca. O Companion executa.

## Trade-offs

- Requer uma representacao formal dos conceitos fundamentais e suas relacoes (o Knowledge Graph do Seedlight) para garantir que todos os caminhos cubram o essencial
- A complexidade combinatoria de "multiplos caminhos para os mesmos fundamentos" e alta — o Curriculum Engine precisa de um algoritmo de planning robusto
- Risco de a crianca ficar num caminho que nao converge para fundamentos essenciais — o BKT + Knowledge Graph precisam detectar gaps
- Os tres componentes (Context Adapter + BKT + Curriculum Engine) precisam de um protocolo de comunicacao claro — o orchestrator e central

## Status

Hipotese arquitetural. Define a filosofia do Curriculum Engine como mundo aberto. Validacao depende do design do Knowledge Graph (Fase 3) e da capacidade do sistema de gerar caminhos personalizados que garantam cobertura.
