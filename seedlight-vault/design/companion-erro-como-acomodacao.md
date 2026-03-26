---
seedlight-component: companion
status: hypothesis
based-on: ["[[esquemas-mentais]]"]
tags: [foundational, scaffolding]
---

# Companion — Erro como Gatilho de Acomodacao

## Decisao / Hipotese

Quando a crianca erra, o Companion **nao deve corrigir diretamente**. Em vez disso, deve criar condicoes para que a crianca perceba o erro por conta propria, forcando acomodacao em vez de assimilacao superficial.

A diferenca pratica:
- **Correcao direta**: "Nao, isso e um cavalo, nao um cachorro" → a crianca memoriza a excecao mas pode nao reorganizar o esquema. Assimilacao disfarçada
- **Gatilho de acomodacao**: "Olha o tamanho dele comparado com um cachorro. E o som que ele faz? E o que as pessoas fazem com ele?" → a crianca percebe que o esquema antigo nao funciona e reorganiza por conta propria

O segundo caminho e mais lento e mais dificil de implementar, mas produz aprendizagem real. E exatamente o que separa um tutor bom de um tutor medioce.

## Fundamentacao

O conceito de [[esquemas-mentais]] de Piaget distingue assimilacao (encaixar no esquema existente) de acomodacao (reorganizar esquemas). Aprendizagem profunda acontece na acomodacao, mas acomodacao exige esforço cognitivo — a crianca naturalmente prefere assimilar. O tutor precisa criar situacoes onde a assimilacao falha.

Isso conecta com o [[two-sigma-problem]]: feedback imediato nao significa correcao imediata. Significa criar o *momento* de aprendizagem imediatamente apos o erro, mas atraves de perguntas e contraexemplos que levam a crianca a perceber a falha no proprio raciocinio.

A nota [[companion-checkpoints-vs-inferencia]] levanta a questao de como verificar dominio — esta nota complementa: a forma de *responder* a erros tambem determina a profundidade do aprendizado.

## Trade-offs

- Requer que o LLM gere perguntas socraticas contextualizadas, nao apenas respostas corretas — mais exigente em termos de capacidade do modelo
- Mais lento que correcao direta, o que tensiona com engajamento (a crianca pode se frustrar)
- Precisa distinguir quando usar esta abordagem (erros conceituais) vs quando correcao direta e adequada (erros factuais simples, como "2+2=5")
- Conecta com Productive Failure (Kapur, area 1.2) que formaliza quando fracasso e produtivo vs improdutivo

## Status

Hipotese. Define o comportamento padrao do Companion diante de erros. Validacao depende da capacidade de modelos pequenos gerarem perguntas socraticas de qualidade (Fase 2).
