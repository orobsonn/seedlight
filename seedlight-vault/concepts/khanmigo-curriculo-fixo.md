---
kind: case-study
sources: ["[[khanmigo-2024]]"]
seedlight-component: all
tags: [scaffolding]
---

# Khanmigo — ITS com LLM em Escala (Khan Academy)

## O que e

Khanmigo e o tutor de IA da Khan Academy, lancado em 2023 com GPT-4. E o maior ITS com LLM em producao real, com milhoes de usuarios. Decisoes arquiteturais:

- LLM na nuvem (GPT-4) — requer internet
- Curriculo **fixo** — segue a arvore de conteudo da Khan Academy
- Avaliacao baseada nos exercicios existentes da plataforma — nao e stealth
- Sem modelo persistente do aluno alem do historico de exercicios
- Prompt engineering pesado pra controlar comportamento ("nunca de a resposta")

**Onde funciona:** matematica estruturada, aluno ja motivado, complemento ao conteudo existente.

**Onde tem problemas:** hallucination em explicacoes, dificuldade com criancas mais novas (chat textual exige literacia), sem adaptacao real (nao sabe o que o aluno sabe), curriculo rigido.

A premissa do Khanmigo e: o conhecimento esta organizado numa arvore, a crianca sobe a arvore com ajuda do LLM. O LLM e um *intermediario* entre a crianca e o conteudo predefinido.

## Por que importa para o Seedlight

O Seedlight difere na premissa fundamental: o curriculo nao e uma arvore fixa, e um grafo que **emerge do contexto da crianca** ([[construcionismo]], Emergent Curriculum). O LLM nao e intermediario pra conteudo predefinido — e companheiro que explora o mundo junto com a crianca.

Diferencas concretas: Seedlight tem BKT como modelo persistente (Khanmigo nao), usa [[stealth-assessment]] em vez de exercicios explicitos, funciona offline (Khanmigo requer nuvem), e o curriculo cresce com a crianca em vez de ser percorrido.

Khanmigo valida que ITS+LLM funciona em escala — mas mostra os limites de colocar LLM como interface pra um sistema que continua fundamentalmente tradicional.
