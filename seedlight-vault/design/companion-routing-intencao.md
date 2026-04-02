---
seedlight-component: companion
status: hypothesis
based-on: ["[[feedback-formativo-vs-somativo]]", "[[its-estrategista-executor]]", "[[bkt-graphrag-complementaridade]]"]
tags: [scaffolding, on-device]
---

# Routing de Intencao no Companion

## Decisao / Hipotese

O Companion deve ter um router que classifica a intencao da crianca antes de decidir qual pipeline aciona. Nem toda interacao precisa de GraphRAG — forcar retrieval em toda resposta mata a naturalidade do dialogo.

Classificacao proposta:
- **Dominio educacional** ("por que chove?") → GraphRAG obrigatorio → Harness monta contexto → LLM responde com base no grafo. Se nao encontrou, diz que nao sabe
- **Dialogo/emocional** ("estou triste") → LLM responde direto, sem retrieval. Empatia, encorajamento, presenca
- **Metacognitivo** ("eu sei isso?") → BKT + OLM → Harness monta resposta sobre estado do aluno
- **Fora de escopo** → "Nao sei, mas podemos descobrir juntos"

## Fundamentacao

Liang et al. (2023) mostraram que o risco de hallucination e alto em dominios abertos — exatamente o territorio do Emergent Curriculum. RAG obrigatorio pra conteudo educacional previne isso. Mas aplicar RAG em interacoes emocionais ou de dialogo e desnecessario e atrapalha a naturalidade.

O padrao de routing alinha com Building Effective Agents (Anthropic): classificador leve na frente que direciona pra pipeline especializada. Pode ser implementado como SLM pequena, heuristica, ou ate regex pra casos obvios.

## Trade-offs

- **Classificacao errada:** se o router classifica "por que o ceu e azul?" como dialogo em vez de dominio, o LLM responde sem RAG e pode alucinar. Erro conservador (tratar como dominio na duvida) e mais seguro
- **Custo do router:** mais um componente rodando no dispositivo. Precisa ser extremamente leve
- **Fronteiras nebulosas:** "estou triste porque nao consigo aprender fracoes" e emocional E dominio. O router precisa lidar com intencoes mistas

## Status

Hipotese. Implementacao concreta do router sera definida na Area 4 (Arquitetura de Agentes).
