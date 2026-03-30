---
kind: framework
sources: ["[[mitchell-2019-model-cards]]"]
seedlight-component: all
tags: [fairness, foundational]
---

# Model Cards

## O que e

Framework de Mitchell et al. (2019) para documentacao de modelos de ML. Assim como um produto tem ficha tecnica, todo modelo deveria ter um "cartao" documentando o que faz, pra quem, e **onde falha**. A diferenca entre documentacao tecnica e Model Card: documentacao diz "como funciona", Model Card diz "quando nao confiar".

### 7 Secoes

1. **Model Details** — o basico (o que e, versao, quem treinou)
2. **Intended Use** — pra que serve e pra que NAO serve
3. **Factors** — que caracteristicas das pessoas afetam o desempenho
4. **Metrics** — como medir se ta funcionando (e qual metrica e prioritaria)
5. **Training/Evaluation Data** — com quem foi treinado e testado
6. **Ethical Considerations** — riscos conhecidos
7. **Caveats and Recommendations** — quando nao usar

## Por que importa para o Seedlight

O Seedlight tem pelo menos 4 modelos rodando (BKT, Engagement Detector, LLM do Companion, Context Adapter). Cada um precisa de Model Card. Transforma conhecimento teorico de fairness em **alerta pratico** pra quem implanta o sistema numa comunidade nova. Sem Model Cards, a pessoa que implanta nao sabe onde o modelo falha — e descobre com criancas reais. Detalhamento do BKT em [[bkt-model-card]].
