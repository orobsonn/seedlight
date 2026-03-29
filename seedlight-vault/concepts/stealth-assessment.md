---
kind: technique
sources: ["[[shute-stealth-assessment]]"]
seedlight-component: companion
tags: [assessment, foundational]
---

# Stealth Assessment (Shute)

## O que e

Avaliacao embutida na atividade, invisivel pro aluno. A tarefa tem dupla funcao: pra crianca e atividade (jogar, construir, explorar), pro sistema e coleta de evidencia. A crianca nunca percebe que esta sendo avaliada — nao ha prova, nao ha momento de "agora vou te testar".

Shute formaliza o que [[construcionismo]] de Papert sugere implicitamente: se a crianca esta construindo num micromundo, suas acoes revelam seu estado cognitivo. Stealth Assessment transforma essa observacao em framework de design.

### Quatro elementos

1. **Competency Model** — o que queremos medir. Mapeamento direto pro Student Model do [[evidence-centered-design]]. Quais conhecimentos, habilidades, estados cognitivos estao sendo rastreados

2. **Task Templates** — tarefas que parecem atividade normal mas sao projetadas pra forcar o uso de competencias especificas. A crianca nao percebe que a tarefa foi escolhida por razao pedagogica — pra ela e so o proximo passo natural da atividade

3. **Evidence Rules** — regras que interpretam acoes dentro da tarefa. Nao so acertou/errou, mas: quanto tempo demorou? Tentou antes de pedir ajuda? Mudou de estrategia? Usou conceito X pra resolver problema que exigia conceito Y? E a camada que traduz interacao rica e ambigua em sinal diagnostico

4. **Feedback Loop invisivel** — o sistema ajusta a proxima tarefa com base na evidencia coletada, sem explicitar. A dificuldade muda, o contexto muda, mas a crianca so percebe que a atividade continua. Na pratica e scaffolding adaptativo continuo — o mesmo fluxo de diagnostico e ajuste que ja existe no design do Companion

## Por que importa para o Seedlight

Stealth Assessment e o mecanismo central de avaliacao do Seedlight. Sem provas nem notas, toda avaliacao precisa ser stealth por definicao. Os micromundos de Papert sao o ambiente natural pra isso — a crianca constroi, explora, testa hipoteses, e o sistema observa e interpreta continuamente.

A conexao com [[desirable-difficulties]] e importante: sessoes de revisao espacada tambem sao oportunidades de stealth assessment. O Companion pode avaliar retencao durante retrieval practice sem que a crianca perceba que esta sendo testada — pra ela e so mais uma interacao.

O desafio critico e a qualidade das evidence rules: em interacao aberta, interpretar acoes e inerentemente mais dificil do que corrigir uma prova. A camada de evidence rules — implementada como tool do Companion (ver [[companion-evidence-rules]]) — precisa ser robusta o suficiente pra extrair sinal diagnostico de interacoes ambiguas.
