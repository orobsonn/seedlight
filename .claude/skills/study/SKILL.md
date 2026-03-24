---
name: study
description: Inicia sessao de estudo do Seedlight. Use quando for estudar um paper, repo, livro ou conceito do guia de estudos.
---

# Sessao de Estudo — Seedlight

Voce esta iniciando uma sessao de estudo conjunto para o projeto Seedlight.

## Setup da Sessao

1. Leia `seedlight-vault/dashboard.md` para saber o progresso atual
2. Leia a entry mais recente de `seedlight-vault/journal/` (o arquivo com data mais recente) para recuperar contexto da ultima sessao
3. Verifique se a ultima sessao teve `/review`. Se nao, alerte o usuario e proponha rodar `/review` primeiro
4. Pergunte ao usuario o que ele quer estudar hoje. Se ele trouxer um paper/repo, ofereca para criar a nota de Source

## Durante o Estudo

- Leia o material junto com o usuario (PDFs via Read tool, repos via WebFetch ou Agent)
- Atue como mentor: questione entendimentos, faca perguntas socraticas, aponte quando algo parece errado. NAO concorde por conveniencia
- Quando surgir um conceito relevante para o Seedlight, proponha: "Isso parece um [kind] — quer que eu registre com /insight?"
- Quando perceber conexao com conceito ja registrado no vault, aponte a conexao

## Criando uma Source Note

Se for material novo, crie a nota de source no vault:
- Papers: `seedlight-vault/sources/papers/autor-ano-titulo-curto.md`
- Repos: `seedlight-vault/sources/repos/nome-do-repo.md`
- Livros: `seedlight-vault/sources/books/titulo-curto.md`

Use o template correspondente de `seedlight-vault/templates/`. Preencha os campos do frontmatter.

## Convencoes

- Nomes de arquivo: kebab-case, lowercase, sem acentos
- Frontmatter: consulte CLAUDE.md para campos validos
- Links: NUNCA criar link sem frase que explique POR QUE o link existe
- Tags: vocabulario fechado (ver CLAUDE.md), maximo 3-4 por nota

## Referencia

- Guia de estudos: `docs/seedlight-study-guide-v3.md`
- Spec completa: `docs/superpowers/specs/2026-03-24-study-tracking-system-design.md`
- Vault: `seedlight-vault/`
