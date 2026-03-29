---
kind: framework
sources: ["[[mislevy-ecd]]"]
seedlight-component: bkt
tags: [assessment, foundational]
---

# Evidence-Centered Design (Mislevy et al.)

## O que e

Framework de engenharia de avaliacao que transforma o [[triangulo-avaliacao]] (cognicao, observacao, interpretacao) em algo construivel. Operacionaliza os tres vertices em tres modelos:

### Os tres modelos

1. **Student Model (Modelo do Aluno)** — que variaveis cognitivas estamos rastreando? Quais conhecimentos, habilidades, estados? No Seedlight, e o que o BKT mantem: P(L) para cada conceito no grafo de conhecimento. O GraphRAG fornece a estrutura (quais conceitos existem e como se relacionam), o BKT fornece o estado (quanto o aluno domina cada um)

2. **Task Model (Modelo de Tarefa)** — que tarefas produzem evidencia sobre essas variaveis? Que caracteristicas uma tarefa precisa ter pra revelar se o aluno sabe ou nao sabe? No Seedlight, e o tipo de interacao que o Companion cria, adaptado pelo Context Adapter ao mundo da crianca. A tarefa tem dupla funcao: pra crianca e atividade, pro sistema e coleta de evidencia

3. **Evidence Model (Modelo de Evidencia)** — regras que conectam o que o aluno fez na tarefa com o que isso diz sobre o estado cognitivo. "Se a crianca fez X na tarefa Y, entao P(L) do conceito Z atualiza assim." No Seedlight, e a camada que traduz interacao aberta (ambigua) em sinais binarios (acertou/errou) que o BKT consegue consumir

### Mapeamento para componentes Seedlight

| Modelo ECD | Componente Seedlight |
|------------|---------------------|
| Student Model | BKT (estado) + GraphRAG (estrutura) |
| Task Model | Companion (gera interacao) + Context Adapter (adapta ao contexto) |
| Evidence Model | Evidence rules — tool do Companion que traduz interacao aberta em sinal pro BKT |

### Lacuna identificada

O Evidence Model e onde nenhum componente original do Seedlight cobria bem. O BKT classico espera input binario (acertou/errou), mas numa conversa aberta ou micromundo a interacao e ambigua. A camada de evidence rules resolve essa lacuna — ver [[companion-evidence-rules]].

## Por que importa para o Seedlight

Sem ECD, o risco e construir componentes que nao se encaixam: um BKT que espera dados que o Companion nao produz, ou um Companion que gera interacoes ricas mas sem valor diagnostico. O ECD forca o alinhamento entre o que queremos medir, como provocamos evidencia, e como interpretamos o resultado. E o framework que garante que a [[stealth-assessment]] funcione na pratica.
