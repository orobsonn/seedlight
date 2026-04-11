---
seedlight-component: companion
status: hypothesis
based-on: ["[[its-estrategista-executor]]", "[[bkt-graphrag-complementaridade]]", "[[grpo-rl-economico]]"]
tags: #critical
---

# Pipeline Incremental de Deploy (V1 → V2 → V3)

## Decisao / Hipotese

O deploy do Companion nao precisa implementar toda a complexidade de uma vez. Tres versoes incrementais, cada uma adicionando capacidade:

**V1 — SFT + RL simples**
- Modelo treinado com dialogos educacionais (SFT) e refinado com GRPO usando reward functions pedagogicas
- Sem tool use, sem busca em grafo
- Entrega: tom adequado, scaffolding, nivel adequado, tutoring moves
- Ja funcional como tutor basico

**V2 — RAG no harness**
- O [[companion-harness-estrategista]] busca contexto no GraphRAG e injeta no prompt do modelo
- Modelo nao precisa "aprender" a buscar — recebe contexto pronto
- O padrao estrategista-executor resolve a complexidade de busca sem treinar o modelo pra isso
- Entrega: respostas ancoradas em conteudo verificado, reducao significativa de alucinacao

**V3 — RL com tool use (futuro)**
- Modelo treinado com RL end-to-end pra usar GraphRAG como ferramenta (inspirado em DeepResearcher/Search-R1)
- So se V2 mostrar que o modelo se beneficiaria de controlar a busca
- Complexidade alta: espaco de acoes explode, treinamento mais instavel

## Fundamentacao

V2 e provavelmente o ponto de equilibrio duradouro. O harness estrategista decide *quando* e *o que* buscar, o modelo faz o dialogo. Cada componente no que e bom. A complexidade de RL com tool use so se justifica se houver evidencia de que o harness nao consegue antecipar as necessidades de busca.

## Trade-offs

- (+) Entrega valor desde V1 — nao precisa esperar pipeline completo
- (+) Cada versao valida premissas da proxima
- (+) V2 resolve 90% dos casos de alucinacao sem complexidade de V3
- (-) V1 sem RAG vai alucinar em conteudo factual — aceitavel como MVP pra validar o resto
- (-) Transicao V2→V3 pode exigir re-treinamento significativo

## Status

Hipotese. V1 e o alvo imediato do pipeline de treinamento (Area 5.3). V2 depende de GraphRAG funcional (Area 3). V3 e pesquisa futura.
