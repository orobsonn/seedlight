---
seedlight-component: context-adapter
status: hypothesis
based-on: ["[[construcionismo]]", "[[esquemas-mentais]]", "[[cognicao-situada]]"]
tags: [foundational, offline-first]
---

# Curriculum — Conhecimento Local Vem da Crianca, Nao do Sistema

## Decisao / Hipotese

O Seedlight carrega **fundamentos universais** (conceitos, frameworks, relacoes entre areas de conhecimento) mas nao tenta armazenar conhecimento especifico de cada regiao do mundo. O contexto local — a historia, a geografia, a cultura do lugar onde a crianca vive — vem **da propria crianca** pela interacao natural.

Divisao de responsabilidade:

- **Sistema**: fundamentos universais (ciclo da agua, formacao de civilizacoes, principios de fisica, matematica)
- **Crianca**: contexto local (o acude secou, a feira e no sabado, o rio encheu)
- **Context Adapter**: captura o contexto local ao longo do tempo e conecta com os fundamentos universais, criando pontes personalizadas

Exemplo: a crianca diz "a agua do acude secou". O Companion nao precisa saber a historia hidrica de Campina Grande. Ele usa isso como porta de entrada para ciclo da agua, evaporacao, clima semiarido — conectando o esquema local da crianca com conceitos universais.

## Fundamentacao

O [[construcionismo]] de Papert e o principio [[curriculum-esquema-antes-assunto]] estabelecem que a porta de entrada para o conhecimento deve ser o mundo da crianca. Mas armazenar todo o conhecimento local de cada regiao e inviavel para um sistema on-device num Raspberry Pi com modelo de 1-3B.

A solucao e arquiteturalmente elegante: os [[esquemas-mentais]] da crianca ja carregam o conhecimento local. O Context Adapter precisa apenas **ouvir e conectar**, nao armazenar. Isso inverte a carga: o sistema e leve (fundamentos universais), e o conhecimento local emerge da interacao, capturado pelo GraphRAG no Learner Profile.

A [[cognicao-situada]] de Lave fornece a fundamentacao teorica formal: se conhecimento e inseparavel do contexto onde foi produzido, ensinar sem o contexto da crianca nao e apenas "menos interessante" — e ensinar no vacuo. O Context Adapter nao "personaliza exemplos" de conceitos abstratos; ele garante que o conhecimento **nasce** no contexto da crianca. Sem o acude de Campina Grande, o conceito de evaporacao nao gruda — fica conhecimento escolar que nao transfere, como as fracoes da dona de casa no supermercado vs na escola.

## Trade-offs

- Depende da qualidade da captura de contexto pelo Context Adapter — se ele nao captura bem, o sistema perde a conexao local
- Criancas muito novas podem nao verbalizar contexto suficiente — o sistema precisa de estrategias ativas de elicitacao
- Conceitos universais sem contexto local podem parecer abstratos e desengajantes — o Companion precisa ativamente buscar pontes
- A fronteira entre "fundamento universal" e "conhecimento local" nem sempre e clara

## Status

Hipotese. Resolve a tensao entre riqueza pedagogica e restricao de hardware. Validacao depende do design do Context Adapter (Fase 3).
