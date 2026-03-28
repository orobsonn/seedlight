---
seedlight-component: companion
status: hypothesis
based-on: ["[[mastery-learning]]", "[[two-sigma-problem]]"]
tags: [foundational, scaffolding]
---

# Companion — Desbloqueio das 4 Barreiras do Mastery Learning

## Decisao / Hipotese

O Mastery Learning (Bloom 1968) provou que dominio antes de avanco produz ~1 sigma de melhoria, mas nao escalou porque exige 4 capacidades que um professor sozinho com 30 alunos nao consegue manter simultaneamente. O Companion resolve cada uma:

| Barreira do professor | Como o Companion resolve | Componente |
|---|---|---|
| Criar avaliacao formativa por unidade | Gera dinamicamente, stealth assessment embutido na interacao | LLM + BKT |
| Diagnosticar individualmente cada aluno | BKT rodando em tempo real, ciclo continuo | BKT |
| Preparar correctives diferenciados | LLM gera explicacoes alternativas sob demanda — caminhos diferentes, nao repeticao | LLM |
| Gerenciar multiplos ritmos simultaneamente | Cada crianca tem seu proprio Companion, ritmo individual por design | Arquitetura 1-a-1 |

## Fundamentacao

O [[two-sigma-problem]] mostrou que mesmo com Mastery Learning, faltava 1 sigma pra igualar tutoria 1-a-1. Esse gap vem dos mecanismos do tutor humano que o professor em sala nao replica: diagnostico continuo fino, scaffolding calibrado e engajamento individual. O Companion nao apenas desbloqueio as barreiras do Mastery Learning — ele tambem adiciona os mecanismos do tutor que fecham o gap restante, conforme mapeado em [[companion-cadeia-diagnostico-scaffolding-pacing]].

A [[aptidao-como-velocidade]] de Bloom fundamenta por que a barreira de "gerenciar ritmos" e critica: se aptidao e velocidade, um sistema que forca ritmo unico esta sistematicamente prejudicando quem precisa de mais tempo. O Companion individual elimina essa restricao por arquitetura.

## Trade-offs

- A qualidade dos correctives depende da capacidade do LLM — modelos pequenos (1-3B) podem nao gerar explicacoes alternativas com qualidade suficiente. Tensao aberta pra Fase 2
- Stealth assessment exige design cuidadoso pra nao transformar toda interacao em avaliacao disfarçada — risco de quebrar confianca
- O Companion assume o papel do professor nos correctives, mas nao tem o repertorio de estrategias pedagogicas de um professor experiente — depende do treinamento (RL) pra desenvolver isso

## Status

Hipotese. Validacao depende da capacidade real do LLM no dispositivo (Fase 2) e do design do orchestrator (Fase 3).
