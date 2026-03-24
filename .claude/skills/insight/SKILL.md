---
name: insight
description: Registra um insight no vault do Seedlight com classificacao e links. Use durante sessoes de estudo quando surgir um conceito ou decisao de design relevante.
---

# Registrar Insight — Seedlight

O usuario quer registrar um insight no vault. Pode ser um conceito extraido de um paper, um padrao arquitetural de um repo, uma decisao de design, ou qualquer conhecimento relevante para o Seedlight.

## Fluxo

1. **Receba o insight** — o usuario descreve ou voce propoe baseado na conversa
2. **Classifique:**
   - `kind`: principle | framework | metric | pattern | antipattern | sequence | technique | constraint | case-study | lesson
   - `seedlight-component`: companion | curriculum | bkt | graphrag | context-adapter | engagement | equity-layer | orchestrator | ui | infra | all
   - Pergunte ao usuario se a classificacao nao for obvia
3. **Busque conexoes** — leia o frontmatter das notas existentes em `seedlight-vault/concepts/` e `seedlight-vault/design/` para identificar notas que podem se conectar
4. **Decida o tipo de nota:**
   - Se e um conceito extraido de estudo → `concepts/nome-do-conceito.md`
   - Se e uma decisao/hipotese de design para o Seedlight → `design/componente-decisao.md`
5. **Crie a nota** usando o template de `seedlight-vault/templates/concept.md` ou `design.md`
6. **Escreva o conteudo** com links contextualizados para notas relacionadas. Cada link deve estar dentro de uma frase que explica a relacao
7. **Atualize notas relacionadas** — se faz sentido, adicione um backlink com contexto nas notas existentes que se conectam
8. **Atualize dashboard.md** — incremente o contador relevante em `seedlight-vault/dashboard.md`

## Convencoes

- Nomes de arquivo: kebab-case, lowercase, sem acentos
- NUNCA criar link sem frase que explique a relacao
- Links em prosa contextualizada, NUNCA em listas soltas
- Tags: vocabulario fechado (ver CLAUDE.md), maximo 3-4 por nota
- Cada nota de concept DEVE ter a secao "Por que importa para o Seedlight" — se nao importa, talvez nao mereca uma nota

## Referencia

- Spec: `docs/superpowers/specs/2026-03-24-study-tracking-system-design.md`
- Vault: `seedlight-vault/`
