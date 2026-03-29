---
type: paper
areas: ["6.1"]
status: done
---

# On the (im)possibility of fairness — Friedler, Scheidegger & Venkatasubramanian (2016)

## Referencia

Friedler, Sorelle A., Carlos Scheidegger, and Suresh Venkatasubramanian. "On the (im)possibility of fairness." arXiv preprint, 2016.

## Tese Central

Diferentes definicoes matematicas de fairness sao mutuamente exclusivas — exceto em casos triviais, nao e possivel satisfazer todas ao mesmo tempo. Isso forca escolhas explicitas.

## Tres Definicoes Centrais

- **Demographic Parity** — resultados iguais entre grupos (mesma % de "aptos" entre subpopulacoes)
- **Equal Opportunity** — mesma taxa de acerto entre grupos (se a crianca sabe, o sistema reconhece independente do grupo)
- **Calibration** — quando o sistema diz "80% de chance", isso e verdade pra todos os grupos

## Conceitos Extraidos

A impossibilidade de satisfazer todas as definicoes simultaneamente foi extraida como constraint em [[impossibilidade-de-fairness]]. A escolha de equal opportunity como prioridade do Seedlight esta documentada em [[equity-layer-fairness-metric]], alinhada com o principio de Aequitas de que em intervencao assistiva o erro mais grave e o falso negativo.
