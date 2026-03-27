---
seedlight-component: companion
status: hypothesis
based-on: ["[[esquemas-mentais]]", "[[zona-desenvolvimento-proximal]]"]
tags: [foundational, scaffolding]
---

# Companion — Quem Verbaliza a Conclusao e Quem Aprende

## Decisao / Hipotese

O Companion **nunca deve entregar a conclusao**. O scaffolding deve ser construido de forma que a crianca seja quem verbaliza o insight, porque e a verbalizacao que consolida a acomodacao do esquema.

A regra pratica:
- **Errado**: Companion faz perguntas e depois entrega a resposta quando a crianca nao chega la
- **Errado**: Companion diz "talvez isso nao seja X" — correcao indireta ainda e correcao
- **Certo**: Companion faz perguntas que levam a crianca a verbalizar a conclusao por conta propria

Exemplo concreto: crianca monta blocos e diz "fiz uma casa". O Companion nao diz "talvez nao seja uma casa". Pergunta: "E a porta, onde fica? Como voce entra na sua casa?" — a crianca olha e percebe sozinha que falta algo. O esquema "casa" se reorganiza sem correcao externa.

## Fundamentacao

A nota [[companion-erro-como-acomodacao]] define que o Companion deve criar condicoes para acomodacao em vez de corrigir diretamente. Este insight refina o *mecanismo*: nao basta fazer perguntas — o scaffolding precisa ser desenhado para que a **crianca** seja quem fala a conclusao, nao o Companion. A diferenca e sutil mas critica: uma correcao indireta ("talvez isso nao seja X") ainda e o Companion entregando a resposta, so que de forma velada.

Isso se conecta com o scaffolding da [[zona-desenvolvimento-proximal]]: o suporte deve ser dosado para que a crianca consiga dar o ultimo passo sozinha. E na cadeia [[companion-cadeia-diagnostico-scaffolding-pacing]], o diagnostico precisa detectar nao so se a crianca entendeu, mas se ela *verbalizou* o entendimento — a verbalizacao e evidencia mais forte de acomodacao do que uma resposta correta a uma pergunta fechada.

A tecnica principal e a **pergunta socratica contextualizada**: perguntas que conectam com a experiencia da crianca e a guiam ate o ponto onde ela mesma enuncia o conceito. Isso tambem respeita os [[companion-estagios-cognitivos]] — no pre-operatorio, as perguntas devem referenciar experiencia vivida ("voce ja viu..."), nao logica abstrata.

## Trade-offs

- Exige que o LLM gere perguntas socraticas de alta qualidade e contextualizadas — mais exigente que correcao direta ou indireta
- Mais demorado: a crianca pode precisar de varias rodadas de perguntas antes de verbalizar. Tensiona com engajamento
- Ha momentos onde correcao direta e adequada (erros factuais simples, seguranca) — a regra nao e absoluta
- A deteccao de "a crianca verbalizou a conclusao" e um desafio de NLU para modelos pequenos

## Status

Hipotese. Refina o comportamento de scaffolding do Companion. Validacao depende da capacidade de modelos pequenos gerarem perguntas socraticas contextualizadas (Fase 2).
