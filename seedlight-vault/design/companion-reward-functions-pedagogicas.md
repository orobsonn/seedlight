---
seedlight-component: companion
status: hypothesis
based-on: ["[[zona-desenvolvimento-proximal]]", "[[tutoring-moves]]", "[[motivacao-intrinseca-sdt]]", "[[bkt-mecanica]]", "[[productive-failure]]"]
tags: #foundational
---

# Reward Functions Pedagogicas para RL

## Decisao / Hipotese

As reward functions do pipeline GRPO devem codificar os principios educacionais da Fase 1 como sinais de recompensa quantificaveis. Quatro dimensoes:

1. **Nivel adequado (ZDP)** — a resposta esta na zona de desenvolvimento proximal da crianca? O [[bkt-mecanica]] fornece o estado de dominio por knowledge component (P(L)), funcionando como "mapa da ZDP" que o reward model consulta. Resposta que assume conceitos nao dominados e penalizada.

2. **Scaffolding correto** — o modelo usou [[tutoring-moves]] adequados? Deu hint em vez de resposta pronta? Usou pumping, prompting, em vez de tell? O [[productive-failure]] define quando deixar errar e quando intervir.

3. **Motivacao preservada** — a resposta respeita autonomia, competencia e conexao ([[motivacao-intrinseca-sdt]])? Encorajadora sem condescendencia? Sem [[undermining-effect]]?

4. **Correcao factual** — o conteudo esta correto? Metrica mais simples mas nao menos importante.

## Fundamentacao

Cada dimensao vem diretamente da pesquisa educacional estudada. O BKT como mapa da ZDP e a peca central — transforma avaliacao qualitativa ("esta na ZDP?") em sinal quantitativo (P(L) do conceito usado na resposta vs P(L) da crianca). Durante o treinamento, um BKT simulado com perfis sinteticos de criancas fornece o sinal.

## Trade-offs

- (+) Reward functions fundamentadas em pesquisa, nao arbitrarias
- (+) BKT como proxy quantitativo pra ZDP — mensuravel automaticamente
- (+) Multi-dimensional: modelo precisa ser bom em tudo, nao so num aspecto
- (-) Reward functions compostas sao mais dificeis de balancear (peso de cada dimensao)
- (-) BKT simulado pode nao refletir criancas reais (mesmo risco de dados sinteticos)
- (-) Scaffolding e motivacao sao mais dificeis de avaliar automaticamente que correcao factual

## Status

Hipotese. Depende de: (1) pipeline SFT+RL funcional (Area 5.3), (2) BKT simulado com perfis realistas, (3) metricas automaticas pra scaffolding e motivacao.
