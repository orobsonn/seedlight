---
name: progress
description: Mostra o progresso geral do estudo do Seedlight. Le o dashboard e apresenta visao geral de onde estamos.
disable-model-invocation: true
---

# Progresso de Estudo — Seedlight

O usuario quer ver o estado geral do estudo.

## Modo Padrao (rapido)

1. Leia `seedlight-vault/dashboard.md`
2. Apresente um resumo formatado:
   - Fase atual e progresso dentro dela
   - Areas concluidas vs em andamento vs nao iniciadas
   - Contadores (sources, conceitos, design notes, duvidas abertas)
   - Ultimas sessoes
3. Sugira a proxima area de estudo baseada na ordem do guia e dependencias

## Modo Recalculo (se o usuario pedir "recalcular" ou "recontar")

1. Leia TODOS os arquivos de `seedlight-vault/sources/`, `concepts/`, `design/`, `journal/`
2. Recontabilize tudo a partir do frontmatter
3. Reescreva `seedlight-vault/dashboard.md` com contadores atualizados
4. Apresente o resultado

## Referencia

- Guia de estudos: `docs/seedlight-study-guide-v3.md`
- Vault: `seedlight-vault/`
