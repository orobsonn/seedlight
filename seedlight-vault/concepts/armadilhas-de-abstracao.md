---
kind: framework
sources: ["[[selbst-2019-fairness-abstraction]]"]
seedlight-component: equity-layer
tags: [fairness, foundational]
---

# Armadilhas de Abstracao

## O que e

Framework de Selbst et al. (2019) que identifica 5 armadilhas em que engenheiros caem ao tentar resolver fairness apenas com codigo. A tese central e que fairness nao e propriedade do modelo — e propriedade da relacao entre o sistema tecnico e o contexto social.

### As 5 Armadilhas

1. **Framing Trap** — reduzir fairness a uma metrica de otimizacao. Exemplo no Seedlight: "colocar um threshold de P(know) e considerar 'apto'" — resolve pacing, nao resolve justica.

2. **Portability Trap** — assumir que uma solucao funciona em todos os contextos. Exemplo no Seedlight: calibrar BKT com dados de criancas urbanas e assumir que funciona igual pra rurais.

3. **Formalism Trap** — achar que definicoes matematicas capturam fairness. Exemplo: definir "P(know) igual entre grupos" quando fairness depende de contexto, historia e necessidade — diretamente ligado a [[impossibilidade-de-fairness]].

4. **Ripple Effect Trap** — ignorar que o sistema muda o contexto social. Exemplo no Seedlight: se o Companion da mais atencao a quem esta "atras", pais e escola podem reagir diferente.

5. **Solutionism Trap** — assumir que tecnologia resolve o problema. Crianca com fome aprende menos — nenhum algoritmo muda isso. Mas o sistema precisa **reconhecer** o limite e nao piorar a situacao. Quando o Companion insiste com mais instrucao ignorando que o problema e externo, vira contexto controlador e causa [[undermining-effect]].

## Por que importa para o Seedlight

O Emergent Curriculum e simultaneamente a maior forca e o maior vetor de bias do projeto, como documentado em [[curriculum-vetor-de-bias]]. Cada armadilha mapeia para riscos concretos identificados: caminhos desiguais (trap 1), diversidade dentro do grupo-alvo (trap 2), interpretacao errada de competencia (trap 3), mudanca do contexto social (trap 4) e limites do que tecnologia resolve (trap 5). O engagement detector, originalmente desenhado como componente pedagogico, ganha papel de fairness ao detectar quando problemas sao externos ao sistema — documentado em [[engagement-detector-fairness]].
