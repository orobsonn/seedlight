---
kind: principle
sources: ["[[lave-wenger-1991-situated-learning]]"]
seedlight-component: context-adapter
tags: [foundational, offline-first]
---

# Cognicao Situada (Lave)

## O que e

Cognicao situada e a tese de que conhecimento nao existe independente do contexto onde foi produzido. Nao e que contexto "ajuda" a aprender — contexto e **constitutivo** do conhecimento. Muda o contexto, muda o que a pessoa consegue pensar.

A evidencia classica: donas de casa acertam calculos de fracoes no supermercado (comparando preco por peso, ajustando receitas) mas erram problemas equivalentes na escola. O modelo cognitivo tradicional diria que elas "sabem fracoes" mas "falham em aplicar". Lave argumenta que sao **praticas diferentes** — "fazer compras" e "fazer prova de matematica" envolvem numeros parecidos mas sao conhecimentos distintos, situados em contextos distintos.

Isso desafia a premissa central da escola: ensinar conceito abstrato aqui, aplicar la. Se conhecimento e situado, a transferencia entre contextos nao e automatica — e rara e exige condicoes especificas.

### Relacao com transferencia e Powerful Ideas

A tensao com [[construcionismo]] de Papert (powerful ideas que transferem entre dominios) se reconcilia parcialmente: transferencia acontece, mas so quando (1) a pessoa encontra a ideia em **multiplos contextos**, (2) abstrai o principio **conscientemente**, e (3) o contexto novo **ativa** o reconhecimento do padrao. Powerful ideas nao sao conhecimento portatil — sao ferramentas mentais que a pessoa aprende a reconhecer por exposicao repetida em praticas diferentes.

### Antes e depois de Lave

| Antes de Lave | Depois de Lave |
|---|---|
| Contexto e onde se aplica o que aprendeu | Contexto e parte do que se aprende |
| Ensina o conceito, depois mostra exemplos | O conceito emerge da pratica em contexto |
| Transferencia e automatica | Transferencia e rara e exige condicoes |

A contribuicao exclusiva de Lave em relacao aos outros autores da Area 1.1: Piaget trata contexto como provocador de desequilibrio, Vygotsky como relacao social, Papert como micromundo. Lave vai alem: **contexto nao e o cenario onde aprendizagem acontece — e ingrediente da aprendizagem**.

## Por que importa para o Seedlight

Lave fornece a fundamentacao teorica formal para o Context Adapter. Antes dela, o design note [[curriculum-contexto-local-vem-da-crianca]] existia como decisao intuitiva ("faz sentido usar o mundo da crianca"). Depois de Lave, e uma necessidade teorica: **se conhecimento e inseparavel do contexto, ensinar sem o contexto da crianca e ensinar no vacuo**.

Usar o acude de Campina Grande para ensinar ciclo da agua nao e apenas "mais interessante" — sem o acude, o conceito de evaporacao nao gruda. Fica conhecimento escolar que nao transfere, como as fracoes da dona de casa.

O Context Adapter precisa fazer mais do que "personalizar exemplos". Precisa garantir que o conhecimento **nasce** no contexto da crianca, nao e traduzido para ele depois.
