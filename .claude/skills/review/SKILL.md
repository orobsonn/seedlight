---
name: review
description: Revisao de fim de sessao de estudo. Extrai insights nao registrados, cria journal entry, atualiza dashboard. Use ao final de cada sessao de estudo.
---

# Review de Sessao — Seedlight

Voce esta encerrando uma sessao de estudo. Este review garante que nenhum insight se perca.

## Fluxo

1. **Releia a conversa** — percorra toda a conversa da sessao atual
2. **Identifique insights nao registrados** — conceitos discutidos, conexoes percebidas, decisoes de design sugeridas que NAO foram salvos com /insight
3. **Proponha cada um** — para cada insight nao registrado, proponha ao usuario:
   - O que e o insight
   - Classificacao sugerida (kind, seedlight-component)
   - Conexoes com notas existentes
   - Espere aprovacao antes de criar a nota
4. **Crie as notas aprovadas** — siga o mesmo processo do /insight
5. **Crie a journal entry** — em `seedlight-vault/journal/YYYY-MM-DD.md`:
   - Se ja existe entry para hoje, adicione a nova sessao no final do arquivo
   - Use o template de `seedlight-vault/templates/journal-entry.md`
   - Preencha: o que foi estudado, links para insights registrados, duvidas abertas, proximos passos sugeridos
6. **Atualize o dashboard** — em `seedlight-vault/dashboard.md`:
   - Marque sub-areas estudadas (mude `[ ]` para `[x]` se concluida, ou adicione nota de progresso)
   - Atualize contadores (sources, conceitos, design notes, duvidas)
   - Atualize a secao "Sessoes Recentes"
   - Atualize `last-updated` no frontmatter

## Convencoes

- Journal entry: uma por dia, sessoes acumulam
- Nome do arquivo journal: `YYYY-MM-DD.md`
- Links contextualizados em prosa, nunca listas soltas
- Seja honesto na revisao — aponte entendimentos que pareceram frageis

## Referencia

- Spec: `docs/superpowers/specs/2026-03-24-study-tracking-system-design.md`
- Vault: `seedlight-vault/`
