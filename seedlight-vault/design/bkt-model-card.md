---
seedlight-component: bkt
status: hypothesis
based-on: ["[[model-cards]]", "[[pipeline-bias-educacional]]", "[[representational-vs-historical-bias]]"]
tags: [fairness, assessment, critical]
---

# BKT — Model Card

## Model Details

Bayesian Knowledge Tracing. Estima P(know) — probabilidade de a crianca dominar um conceito. 4 parametros: P(L0) init, P(T) learn, P(G) guess, P(S) slip.

## Intended Use

**Serve para**: avaliar se a crianca entendeu um conceito. E uma engrenagem dentro do Seedlight — seu output alimenta calculo de scaffolding e decisao de pacing.

**NAO serve para**: ser usado como motor de ensino isolado. Nao deve tomar decisoes autonomas sem o orchestrator e o Companion.

## Factors — Caracteristicas que Afetam Confiabilidade

### 1. Calibracao regional (representational bias)

Se calibrado com criancas de uma regiao/perfil especifico, confiabilidade reduzida pra criancas de contextos nao representados no treino. Exemplo: calibrado com criancas urbanas do Sudeste, aplicado em comunidade ribeirinha.

### 2. Neurodivergencia (measurement bias)

Criancas neurodivergentes (autismo, TDAH, etc.) podem dominar conceitos mas demonstrar de forma que as evidence rules nao reconhecem: tempo de resposta atipico, padrao de interacao diferente, expressao emocional nao-padrao. BKT recebe sinal de "nao sabe" quando e "sabe, mas expressa diferente". Falso negativo — o erro mais grave no Seedlight.

### 3. Estado temporario (historical bias)

Crianca cansada, com fome, emocionalmente abalada. Sinais refletem estado, nao conhecimento. BKT nao distingue — ve "errou" e atualiza P(know) pra baixo. Se repetido, modelo degrada progressivamente. Detalhado em [[companion-estado-vs-capacidade]].

## Metrics

Metrica prioritaria: [[equity-layer-fairness-metric|equal opportunity]] — quando a crianca domina um conceito, o BKT deve reconhecer isso independentemente do grupo. Taxa de falso negativo por subgrupo e a auditoria mais importante.

## Ethical Considerations

- Feedback loop: subestimacao alimenta dados que confirmam subestimacao ([[feedback-loop-bias]])
- Dataset gerado em producao pela propria crianca — perfil longitudinal sensivel ([[datasheets-for-datasets]])
- Postura conservadora quando confianca e baixa ([[companion-postura-conservadora]])

## Caveats and Recommendations

Nao implantar em comunidade nova sem recalibrar parametros com dados locais. Monitorar taxa de falso negativo por subgrupo desde o primeiro dia. Se disparidade detectada, investigar etapa 1 (measurement) antes de ajustar etapa 3 (decisao).

## Status

Hipotese. Sera refinado conforme implementacao avanca (Fase 2+ para BKT, Fase 6 para validacao com criancas reais).
