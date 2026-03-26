---
kind: framework
sources: ["[[bloom-1984-two-sigma-problem]]"]
seedlight-component: all
tags: [foundational, scaffolding]
---

# The 2 Sigma Problem

## O que e

Framework de Benjamin Bloom (1984) que demonstra que tutoria individual (1 tutor para 1-3 alunos) com mastery learning produz resultados 2 desvios-padrao acima da instrucao convencional em sala de aula. Isso significa que o aluno medio com tutor supera 98% dos alunos em sala convencional.

O "problema" e que tutoria 1-a-1 nao escala — nao existem tutores suficientes para todas as criancas. Bloom identificou 4 mecanismos que explicam a superioridade do tutor:

1. **Feedback imediato** — erros corrigidos na hora, impedindo construcao de conhecimento sobre fundacao errada
2. **Pacing adaptativo** — o aluno so avanca quando domina o conceito atual
3. **Diagnostico continuo** — o tutor percebe *onde* e *por que* o aluno esta travando, nao apenas *que* errou
4. **Engajamento forcado** — impossivel se esconder, diferente de uma sala com 30 alunos

O engajamento e o mecanismo mais critico porque sem ele os outros 3 nao tem efeito — o melhor feedback do mundo e inutil se a crianca nao esta ali.

## Por que importa para o Seedlight

O 2 Sigma Problem e a justificativa estatistica central do projeto. O Seedlight e uma tentativa de resposta ao problema de Bloom 40 anos depois, usando IA no dispositivo como tutor acessivel. Cada um dos 4 mecanismos mapeia para um componente da arquitetura: feedback imediato depende da qualidade do LLM no dispositivo, pacing adaptativo depende do [[bkt]] como motor de knowledge tracing, diagnostico continuo exige a combinacao de BKT com analise de padroes de resposta, e engajamento depende do [[context-adapter]] para tornar a aprendizagem significativa conectando-a ao mundo da crianca.
