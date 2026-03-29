---
seedlight-component: companion, engagement
status: hypothesis
based-on: ["[[productive-failure]]", "[[companion-contexto-sustentador]]", "[[companion-erro-como-acomodacao]]"]
tags: [scaffolding, assessment]
---

# Companion — Equilibrio entre Suporte e Fracasso Produtivo

## Decisao / Hipotese

O Companion deve equilibrar duas forcas aparentemente contraditorias: ser contexto sustentador (SDT) e permitir fracasso produtivo (Kapur). A resolucao nao e um meio-termo — e uma decisao dinamica baseada em sinal de engajamento em tempo real.

Fluxo operacional:
1. **Conceito novo surge** — Companion nao ensina diretamente. Cria contexto para a crianca tentar (problema acessivel mas nao resolvivel, dentro da ZDP)
2. **Crianca tenta** — Companion observa. O engagement detector monitora estado emocional/motivacional
3. **Decisao em tempo real:**
   - Crianca engajada (tentando abordagens, iterando, perguntando) → productive failure em andamento, nao interromper
   - Crianca desengajando (frustracao, desistencia, respostas aleatorias) → fracasso virando destrutivo, entrar com scaffolding
4. **Consolidacao** — apos a luta, Companion entra como MKO com instrucao formal. O scaffolding e mais preciso porque a tentativa fracassada revelou onde a crianca travou (diagnostico natural)
5. **Excecao: assimilacao pura** — se o BKT indica alta probabilidade de dominio do conceito-base, provavelmente e assimilacao (encaixar no esquema existente). Nesse caso, instrucao direta e adequada

## Fundamentacao

Kapur (2008) demonstrou que fracasso antes de instrucao produz aprendizagem mais profunda ([[productive-failure]]). Mas fracasso sem suporte e destrutivo. SDT ([[companion-contexto-sustentador]]) exige ambiente sustentador. A resolucao e que ser sustentador nao e ser passivo — e criar condicoes onde o fracasso e seguro e produtivo.

O engagement detector e o componente que resolve a tensao na pratica: ele fornece o sinal que o Companion precisa para decidir entre "deixar lutar" e "entrar com scaffolding". Sem esse sinal, a decisao seria arbitraria (baseada em tempo ou numero de erros, que sao proxies ruins).

Isso refina a [[companion-cadeia-diagnostico-scaffolding-pacing]]: o diagnostico continuo nao e apenas BKT (o que a crianca sabe) mas tambem engagement (como a crianca esta). Os dois sinais juntos informam o scaffolding.

## Trade-offs

- O engagement detector precisa ser preciso o suficiente para distinguir frustracao produtiva ("isso e dificil mas eu quero resolver") de frustracao destrutiva ("eu nao consigo e quero parar"). Desafio tecnico para a Fase 2
- Modelos pequenos (1-3B) precisam ser capazes de modular entre "observar sem intervir" e "entrar com scaffolding" — requer controle fino de comportamento
- Risco de calibracao errada em ambas as direcoes: intervir cedo demais (mata productive failure) ou tarde demais (gera frustracao destrutiva)
- Interface: a crianca precisa de canal para sinalizar frustracao voluntariamente ("estou travado") vs o sistema inferir automaticamente

## Status

Hipotese forte. Formaliza a tensao entre suporte e fracasso produtivo com mecanismo de resolucao claro (engagement detector). Validacao depende do engagement detector (Fase 2) e testes com Companion real (Fase 6).
