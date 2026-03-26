---
kind: framework
sources: ["[[bloom-1984-two-sigma-problem]]"]
seedlight-component: companion
tags: [foundational, scaffolding]
---

# Zona de Desenvolvimento Proximal (Vygotsky)

## O que e

Framework de Vygotsky que define tres zonas de conhecimento para qualquer habilidade:

1. **O que a crianca faz sozinha** — ja dominou, nao precisa de ajuda
2. **O que a crianca consegue COM ajuda** — a ZDP, onde aprendizagem acontece
3. **O que a crianca nao consegue nem com ajuda** — longe demais, nao adianta tentar

Tres conceitos integrados formam o sistema de Vygotsky:

- **MKO (More Knowledgeable Other)** — *quem* guia. Alguem (ou algo) que sabe mais e puxa a crianca dentro da ZDP. Funciona por relacao social — a crianca internaliza nao so o conhecimento, mas o processo de pensar com o MKO
- **ZDP** — *onde* o MKO opera. A faixa entre "sei fazer" e "impossivel". Ensinar fora da ZDP e inutil: abaixo e chato, acima e frustrante
- **Scaffolding** — *como* o MKO opera. Suporte gradual que comeca alto e vai sendo retirado conforme a crianca ganha dominio, ate ela operar sozinha

Os tres nao sao conceitos independentes — sao dimensoes do mesmo processo. Sem MKO, ninguem executa. Sem ZDP mapeada, o MKO nao sabe onde atuar. Sem scaffolding, a crianca nao progride mesmo dentro da ZDP.

Diferenca fundamental com Piaget: Piaget via o desenvolvimento como principalmente interno (a crianca constroi esquemas interagindo com o mundo). Vygotsky via como fundamentalmente social (a crianca aprende *atraves* da interacao com alguem mais capaz e depois internaliza). Sao complementares mas com tensao real — Piaget diria que o ambiente importa mais que o tutor, Vygotsky diria o oposto. Papert tentou resolver essa tensao.

## Por que importa para o Seedlight

O Companion precisa integrar as tres dimensoes de Vygotsky como sistema: saber *quem ele e* (MKO funcional com presenca cognitiva construida por memoria persistente e longitudinalidade), *onde atuar* (ZDP mapeada por dominio, nao global — uma crianca pode estar em zonas diferentes para matematica e linguagem), e *como dosar a ajuda* (scaffolding com retirada gradual alimentada pela cadeia diagnostico → scaffolding → pacing).

Isso conecta diretamente com os mecanismos do [[two-sigma-problem]]: pacing adaptativo e a consequencia de operar na ZDP correta, e diagnostico continuo e o sensor que mapeia onde a ZDP esta. O conceito de [[esquemas-mentais]] de Piaget complementa explicando *o que* esta dentro de cada zona — os esquemas que a crianca ja tem (zona 1), os que pode construir com ajuda (ZDP), e os que estao alem da capacidade atual (zona 3).

As decisoes de design derivadas estao em [[companion-cadeia-diagnostico-scaffolding-pacing]] (como os componentes se comunicam), [[companion-mko-funcional]] (natureza do vinculo Companion-crianca) e [[companion-estagios-cognitivos]] (como a ZDP varia por dominio e estagio).
