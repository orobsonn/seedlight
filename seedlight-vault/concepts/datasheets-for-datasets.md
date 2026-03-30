---
kind: framework
sources: ["[[gebru-2021-datasheets-datasets]]"]
seedlight-component: all
tags: [fairness, privacy, foundational]
---

# Datasheets for Datasets

## O que e

Framework de Gebru et al. (2021) para documentacao de datasets. Par do [[model-cards]] — Model Card documenta o modelo, Datasheet documenta os dados. Perguntas centrais: quem coletou, com consentimento, que dados exatamente, o que falta, como pode ser mal-usado.

### Particularidade do Seedlight

O dataset do Seedlight e fundamentalmente diferente de datasets tradicionais (ImageNet, etc.):

- **Gerado em producao** — cada crianca gera dados novos a cada interacao, nao e dataset estatico
- **Alimenta os modelos que geram as proximas interacoes** — feedback loop entre dado e modelo
- **Longitudinal** — anos de interacao, padroes de aprendizagem, estado emocional, contexto familiar
- **O mais sensivel que existe** — perfil completo de uma crianca ao longo de anos. Se vaza, expoe toda a vida da crianca

A decisao arquitetural de manter tudo local no dispositivo, originalmente motivada por offline-first, e na verdade uma decisao de **privacidade**: se o dado nunca sai do dispositivo, o vetor de ataque e fisico, nao remoto.

## Por que importa para o Seedlight

Gebru et al. dizem que o Datasheet precisa documentar riscos de privacidade **desde o design**, nao depois. Conecta com Area 7 (Privacidade e Soberania do Aprendiz, Fase 4) onde isso sera aprofundado. O consentimento informado de pais/responsaveis e pre-requisito — a crianca e familia precisam saber o que o sistema coleta e por que.
