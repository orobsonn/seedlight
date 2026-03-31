---
kind: framework
sources: ["[[vanlehn-2011-its-effectiveness]]", "[[koedinger-2007-cognitive-tutors]]", "[[graesser-2004-autotutor]]"]
seedlight-component: all
tags: #foundational
---

# Mapeamento ITS Classico → Seedlight

## O que e

Intelligent Tutoring Systems classicos tem 4 componentes. O Seedlight herda essa arquitetura, modernizada:

| Componente ITS | Funcao | Seedlight |
|---------------|--------|-----------|
| **Domain Model** | O que o sistema sabe sobre a materia | LLM (sabe explicar) + GraphRAG (sabe a estrutura e dependencias entre conceitos) |
| **Student Model** | O que o sistema acredita que o aluno sabe | BKT (dominio por skill) + Engagement Detector (estado afetivo) + Learner Profile (visao consolidada) |
| **Tutoring Model** | Como o sistema decide ensinar | Harness/Orchestrator (decide nivel de scaffolding, tipo de tutoring move, quando permitir productive failure) |
| **Interface** | Como o aluno interage | TBD — chat funciona pra adultos mas nao pra criancas de 6-10 anos; precisa de algo mais concreto e manipulavel (ver Papert, Piaget estagios) |

A diferenca fundamental do Seedlight em relacao a ITS classicos: o LLM resolve o gargalo de dominios abertos (Cognitive Tutor so funcionava em matematica/programacao) e de linguagem natural (AutoTutor era limitado pela NLP primitiva). Mas o harness mantem a separacao estrategista-executor dos ITS que funcionaram — conforme [[its-estrategista-executor]].

## Por que importa para o Seedlight

Framework de referencia para validar que todos os componentes necessarios existem no design. Se faltar qualquer um dos 4, o sistema nao funciona como tutor. A Interface e o componente mais aberto — a decisao de formato de interacao (Area 11) afeta todo o resto.
