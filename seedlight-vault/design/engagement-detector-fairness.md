---
seedlight-component: engagement, equity-layer
status: hypothesis
based-on: ["[[armadilhas-de-abstracao]]", "[[undermining-effect]]", "[[motivacao-intrinseca-sdt]]"]
tags: [fairness, assessment]
---

# Engagement Detector como Peca de Fairness

## Decisao / Hipotese

O engagement detector nao e apenas componente pedagogico — e peca central de fairness. Ele e o componente que detecta quando o problema e **externo** ao sistema (fome, cansaco, violencia domestica, estresse) e impede que o Companion cause dano adicional.

### Mecanismo

Sem engagement detector com papel de fairness:
1. Crianca para de progredir por razao externa
2. BKT ve P(know) caindo
3. Companion responde com mais scaffolding, mais exercicio, mais repeticao
4. Crianca recebe pressao que nao consegue atender → contexto controlador
5. [[undermining-effect]] — motivacao intrinseca destruida
6. Num sistema longitudinal, esse dano se acumula diariamente

Com engagement detector como peca de fairness:
1. Crianca para de progredir
2. Engagement detector identifica queda sem padrao cognitivo explicavel
3. Companion **recua** — atividade mais leve, sem pressao
4. Sistema pode sinalizar ao cuidador que algo externo pode estar interferindo
5. Motivacao intrinseca preservada

### Conexao com Selbst

Isso e a armadilha 5 (solutionism) na pratica: o sistema nao resolve fome ou violencia, mas precisa **saber que existem** pra nao responder a pergunta errada. A resposta correta do sistema a um problema externo nao e mais instrucao — e recuo protetor.

## Evidencia

Hipotese derivada da conexao entre solutionism trap ([[armadilhas-de-abstracao]]) e undermining effect ([[undermining-effect]]). Design do engagement detector como componente pedagogico ja existe em [[companion-productive-failure]]; este design note expande seu papel para fairness.
