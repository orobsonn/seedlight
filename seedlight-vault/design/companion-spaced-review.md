---
seedlight-component: companion
status: hypothesis
based-on: ["[[desirable-difficulties]]", "[[productive-failure]]", "[[motivacao-intrinseca-sdt]]", "[[construcionismo]]", "[[zona-desenvolvimento-proximal]]"]
tags: [scaffolding, longitudinal]
---

# Companion — Revisao Espacada com Retrieval Practice

## Decisao / Hipotese

O Companion deve implementar um sistema de revisao espacada que usa retrieval practice em contexto engajante, com BKT estendido (decaimento temporal) como sensor e engagement detector como regulador de frustracao.

## Fundamentacao

### Fluxo operacional

1. **BKT com decaimento temporal** detecta que P(L) de um conceito caiu abaixo do threshold de retencao — o aluno provavelmente nao consegue mais recuperar aquele conhecimento
2. **Orchestrator** agenda revisao, aplicando interleaving (mistura conceitos de areas diferentes) e spacing (intervalos crescentes entre revisoes)
3. **Context Adapter** monta sessao de revisao em contexto engajante — nao quiz seco, mas micromundo de revisao alinhado com interesses da crianca, respeitando [[construcionismo]] (a crianca constroi algo que exige o conceito) e [[motivacao-intrinseca-sdt]] (autonomia na escolha, competencia no desafio calibrado)
4. **Companion** aplica retrieval practice primeiro — pede que a crianca recupere da memoria antes de oferecer qualquer re-ensino. Quanto mais dificil a recuperacao, maior o ganho de storage strength
5. **Engagement detector** monitora frustracao. Se a crianca desengaja, o Companion oferece scaffolding progressivo (dica, contexto, ate re-ensino se necessario). A mesma logica de [[productive-failure]] se aplica: dificuldade so e desejavel enquanto ha engajamento
6. **BKT** atualiza P(L) com base na recuperacao. Se bem-sucedida, proximo intervalo de spacing aumenta

### Criterio de consolidacao (anti-loop)

Apos N recuperacoes bem-sucedidas em intervalos crescentes (ex: 3 acertos espacados em 3, 7, 21 dias), o conceito e marcado como **consolidado**. Decaimento para ou se torna tao lento que revisao so seria acionada apos meses. Isso evita o loop infinito de revisao eterna.

### Componentes envolvidos

- **BKT** — sensor de decaimento + atualizador de P(L) pos-revisao
- **Orchestrator** — scheduler de revisoes, aplica spacing e interleaving
- **Context Adapter** — cria contexto engajante para revisao
- **Companion** — executa retrieval practice + scaffolding adaptativo
- **Engagement detector** — regula frustracao, sinaliza quando dificuldade deixou de ser desejavel

## Trade-offs

- **Complexidade vs beneficio**: estender BKT com decaimento adiciona parametro (taxa de decaimento) que precisa ser calibrado. Parametro errado causa revisao cedo demais (desperdicio) ou tarde demais (esquecimento)
- **Tempo de revisao vs conteudo novo**: toda sessao de revisao e tempo que nao esta sendo usado para avancar. O orchestrator precisa balancear revisao e progresso
- **Engajamento vs rigor**: sessao de revisao "divertida" pode nao exercitar retrieval practice real. O desafio e manter engajamento sem perder a dificuldade desejavel

## Status

Hipotese. Parametros de decaimento, thresholds de consolidacao e formato de sessao de revisao serao validados na Fase 2 (Area 2.2 — Knowledge Tracing) e Fase 5 (prototipo).
