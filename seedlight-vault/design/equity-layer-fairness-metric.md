---
seedlight-component: equity-layer, bkt
status: hypothesis
based-on: ["[[impossibilidade-de-fairness]]", "[[armadilhas-de-abstracao]]"]
tags: [fairness, critical]
---

# Equity Layer — Escolha de Fairness Metric

## Decisao / Hipotese

O Seedlight prioriza **equal opportunity** como metrica primaria de fairness: quando uma crianca domina um conceito, o sistema deve reconhecer isso independentemente do grupo a que ela pertence. O sensor (BKT + evidence rules) precisa funcionar bem pra todos os perfis.

### Justificativa

1. **Falso negativo como erro critico** — em intervencao assistiva (educacao), o erro mais grave e nao identificar uma crianca que precisa de apoio. Isso e fundamentalmente diferente de dominios punitivos (justica criminal) onde falso positivo e mais grave. Alinhado com framework Aequitas.

2. **Demographic parity como indicador, nao meta** — forcar resultados numericamente iguais entre grupos pode significar dizer que uma crianca sabe quando nao sabe. A honestidade do sensor e mais importante que igualdade numerica. Porem, disparidade grande entre grupos e sinal de alerta que deve ser investigado.

3. **Calibration como requisito secundario** — o sistema deve ser confiavel em suas estimativas, mas equal opportunity tem precedencia porque protege contra o risco mais concreto no Seedlight: crianca que expressa conhecimento de forma nao-padrao sendo sistematicamente subestimada.

### Implicacoes Praticas

- Evidence rules (tool do Companion, documentadas em [[companion-evidence-rules]]) precisam ser validadas contra diversidade de expressao de competencia — nao apenas padroes urbanos ou de classe media
- Auditoria periodica de taxas de falso negativo por subgrupo e obrigatoria
- A escolha deve ser **declarada publicamente** — nao pode ser implicita no codigo

## Evidencia

Hipotese derivada de [[impossibilidade-de-fairness]] (Friedler) e [[armadilhas-de-abstracao]] (Selbst). Validacao dependera de dados reais na Fase 6.
