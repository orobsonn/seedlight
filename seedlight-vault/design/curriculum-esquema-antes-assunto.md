---
seedlight-component: curriculum
status: hypothesis
based-on: ["[[esquemas-mentais]]"]
tags: [foundational, scaffolding]
---

# Curriculum — Esquema Antes do Assunto

## Decisao / Hipotese

O Emergent Curriculum deve operar na direcao **esquema → assunto**, nao assunto → esquema. Isso significa que o Companion precisa conhecer o mundo da crianca (interesses, contexto, experiencias) *antes* de propor conteudo, e encontrar caminhos naturais dos esquemas existentes ate os conceitos que ela precisa aprender.

A diferenca pratica:
- **Assunto → esquema** (escola tradicional): "Hoje e dia de Bhaskara. Como faço a crianca se interessar?"
- **Esquema → assunto** (Seedlight): "Essa crianca gosta de futebol e quer entender a trajetoria do chute. A matematica dessa curva e uma equacao de segundo grau."

No primeiro caso, o Companion e um professor disfarçado tentando vender conteudo. No segundo, e um tutor que parte da vida real da crianca.

## Fundamentacao

O conceito de [[esquemas-mentais]] de Piaget estabelece que ninguem aprende no vazio — todo conhecimento novo precisa se conectar a esquemas que a crianca ja possui. Se nao ha esquema para conectar, a informacao nao gruda. Isso explica o fenomeno "pra que eu preciso saber Bhaskara?" — a crianca esta dizendo que nao tem esquema para ancorar aquele conteudo.

A nota [[companion-mecanismos-tutoria]] mapeia diagnostico continuo para BKT + analise de padroes, mas esse principio adiciona uma camada anterior: o Companion precisa de um modelo persistente dos esquemas e interesses da crianca para decidir *por onde* introduzir conteudo, nao apenas *quando* avancar.

## Trade-offs

- Requer que o Companion construa e mantenha um modelo do mundo da crianca ao longo do tempo — isso reforça a necessidade de GraphRAG e memoria persistente
- O Context Adapter ganha um papel ainda mais central: nao e so adaptar linguagem, e adaptar o *caminho curricular* inteiro
- Tensao aberta: se o curriculo emerge dos esquemas, como garantir cobertura de conteudo obrigatorio? (a ser explorada quando estudarmos Papert e Emergent Curriculum)

## Status

Hipotese fundamental. Direcao de design que permeia toda a arquitetura do Curriculum Engine e do Context Adapter.
