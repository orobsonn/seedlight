---
kind: constraint
sources: ["[[tack-piech-2022-llm-tutoring]]", "[[liang-2023-llm-assessment]]"]
seedlight-component: companion
tags: [assessment, critical]
---

# Bias Fluencia-Competencia

## O que e

LLMs confundem fluencia verbal com competencia real. Uma crianca articulada parece saber mais para o modelo; uma crianca timida ou com vocabulario limitado parece saber menos. O LLM avalia *linguagem*, nao *conhecimento* — e infere o segundo a partir do primeiro.

Isso nao e uma limitacao de escala que desaparece com modelos maiores. E estrutural: modelos de linguagem processam linguagem. Uma crianca que diz "a agua evapora e depois condensa e chove" parece dominar o ciclo da agua. Uma crianca que diz "a agua sobe e depois cai" pode ter o mesmo entendimento mas recebe avaliacao pior do LLM.

Tack & Piech (2022) identificaram isso como problema central de LLMs em tutoria. Liang et al. (2023) confirmaram que essa limitacao persiste em avaliacao — LLMs sao bons em feedback formativo (qualitativo) mas ruins em somativo (preciso) em parte por causa desse bias.

## Por que importa para o Seedlight

Mais uma razao pela qual o [[bkt-mecanica]] e necessario na arquitetura: BKT avalia *acoes* (acertou, errou, tempo de resposta), nao *palavras*. E imune a fluencia verbal. A divisao de trabalho descrita em [[feedback-formativo-vs-somativo]] — BKT faz somativo, LLM faz formativo — mitiga diretamente esse bias.

Risco especifico para o Seedlight: o Emergent Curriculum atende criancas de contextos diversos, com niveis de literacia e vocabulario muito diferentes. Sem o BKT como ancora, o LLM sistematicamente superestimaria criancas articuladas e subestimaria criancas timidas — exatamente o tipo de [[representational-vs-historical-bias]] que o Equity Layer deve prevenir.
