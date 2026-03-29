---
kind: principle
sources: ["[[bjork-bjork-desirable-difficulties]]"]
seedlight-component: companion
tags: [scaffolding, foundational, assessment]
---

# Desirable Difficulties (Bjork & Bjork)

## O que e

Certas dificuldades introduzidas durante o estudo **parecem prejudicar** o desempenho imediato mas **melhoram** a retencao e transferencia a longo prazo. O efeito e contra-intuitivo: condicoes que tornam a pratica mais fluida (reler, estudar em blocos) produzem ilusao de aprendizagem — o aluno se sente confiante mas esquece rapido.

A distincao central e entre dois tipos de forca da memoria:

- **Storage strength** — quao bem algo foi codificado. Nao diminui com o tempo
- **Retrieval strength** — quao acessivel esta agora. Diminui sem pratica

Desirable difficulties funcionam porque reduzem retrieval strength no curto prazo (parece que voce nao sabe), mas aumentam storage strength (quando a recuperacao e bem-sucedida, a memoria fica mais forte). Quanto mais dificil a recuperacao bem-sucedida, maior o ganho.

### Tres estrategias principais

1. **Spacing (espacamento)** — distribuir estudo no tempo em vez de concentrar. Revisitar em intervalos crescentes (3 dias, 7 dias, 15 dias). Cada revisita e mais dificil porque retrieval strength caiu, mas o esforco de recuperar fortalece storage strength

2. **Interleaving (intercalacao)** — misturar topicos em vez de estudar em blocos. Estudar fracao-geometria-fracao-algebra em vez de fracao-fracao-fracao-geometria. Forca o cerebro a discriminar *entre* conceitos, nao so reconhecer *dentro* de um conceito. Gera "flipagem de estado" que fortalece conexoes

3. **Retrieval practice (pratica de recuperacao)** — puxar da memoria em vez de reler. Tentar lembrar ativamente produz retencao superior a reler o material. Reler gera fluencia ilusoria — a sensacao de que sabe, sem a capacidade de recuperar

### Diferenca fundamental com Productive Failure (Kapur)

[[productive-failure]] opera no momento de **aprender conteudo novo** — fracasso antes de instrucao formal prepara o terreno cognitivo. Desirable difficulties operam no momento de **reter e consolidar conteudo ja aprendido** — como voce pratica e revisita. Sao momentos diferentes do ciclo de aprendizagem e se complementam.

## Por que importa para o Seedlight

O Companion precisa implementar as tres estrategias de Bjork no ciclo de revisao. O risco de nao implementar e que a crianca estude, domine (BKT chega a P(L) > 0.95), mas esqueca semanas depois — e o sistema nao perceba.

A implementacao requer estender o BKT classico com um **fator de decaimento temporal**: se a crianca nao pratica um conceito por tempo suficiente, P(L) decai gradualmente. Quando P(L) cai abaixo de um threshold, o sistema agenda revisao usando retrieval practice (nao re-ensino). A revisao deve acontecer em contexto engajante — nao "responda essa pergunta" mas micromundo de revisao alinhado com [[construcionismo]] e [[motivacao-intrinseca-sdt]].

Um risco de design e o **loop infinito de revisao**: se P(L) sempre decai, a crianca fica presa revisando eternamente. A solucao e um **criterio de consolidacao** — apos N recuperacoes bem-sucedidas espacadas no tempo, o conceito e marcado como consolidado e o decaimento para ou se torna irrelevante.
