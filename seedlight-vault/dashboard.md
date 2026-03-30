---
last-updated: 2026-03-30
---

# Seedlight Study Dashboard

## Visao Geral

| Fase | Nome | Semanas | Status |
|------|------|---------|--------|
| 1 | Fundacao Conceitual | 1-4 | concluida |
| 2 | Hardware e Modelos Pequenos | 5-8 | nao iniciada |
| 3 | Agentes, GraphRAG e Arquitetura | 9-12 | nao iniciada |
| 4 | Infra Offline e Estudos de Caso | 13-16 | nao iniciada |
| 5 | Treinamento e Integracao | 17-20 | nao iniciada |
| 6 | Prototipo Completo | 21-24 | nao iniciada |

---

## Areas de Estudo

### Fase 1 — Fundacao Conceitual (Semanas 1-4)

**Area 1 — Ciencias da Aprendizagem**

1.1 Teorias Fundamentais
- [x] 2 Sigma Problem (Bloom) — por que tutoria 1-a-1 funciona, os 4 mecanismos
- [x] Construtivismo (Piaget) — conhecimento e construido, nao transmitido
  - [x] Esquemas mentais: como o cerebro organiza conhecimento
  - [x] Assimilacao vs Acomodacao: como aprendemos coisas novas
  - [x] Estagios de desenvolvimento: por que idade importa no design
  - [x] Implicacao pro Seedlight: por que o Emergent Curriculum faz sentido
- [x] ZDP (Vygotsky) — a faixa onde aprendizagem acontece
  - [x] Zona de Desenvolvimento Proximal: o que a crianca consegue COM ajuda
  - [x] Scaffolding: como dosar a ajuda e ir retirando
  - [x] Papel do "outro mais capaz": o que o Companion precisa ser
  - [x] Implicacao pro Seedlight: como calibrar o nivel do Companion
- [x] Construcionismo (Papert) — aprender fazendo coisas significativas
  - [x] De Piaget para Papert: o que Papert adicionou
  - [x] Micromundos e "objetos para pensar": ambientes de exploracao
  - [x] Powerful Ideas: ideias que mudam como a crianca pensa
  - [x] Implicacao pro Seedlight: como o curriculo deve emergir
- [x] Situated Learning (Lave & Wenger) — aprendizagem em contexto real
  - [x] Participacao periferica legitima: aprender fazendo de verdade
  - [x] Implicacao pro Seedlight: por que o Context Adapter e essencial

1.2 Aprendizagem Adaptativa e Personalizada
- [x] Mastery Learning (Bloom 1968) — todos aprendem se tiverem tempo e instrucao adequada
  - [x] O principio: ritmo individual vs ritmo da turma
  - [x] Implicacao pro Seedlight: como o BKT implementa pacing adaptativo
- [x] Self-Determination Theory (Ryan & Deci) — motivacao intrinseca
  - [x] Autonomia, competencia e conexao: os 3 pilares
  - [x] Motivacao intrinseca vs extrinseca: por que notas nao funcionam
  - [x] Implicacao pro Seedlight: como substituir notas por significado
- [x] Productive Failure (Kapur) — fracasso que ensina
  - [x] Quando errar e bom: frustacao produtiva vs improdutiva
  - [x] Implicacao pro Seedlight: como o Companion calibra desafios
- [x] Desirable Difficulties (Bjork & Bjork) — dificuldades que melhoram retencao
  - [x] Spacing, interleaving, retrieval practice
  - [x] Implicacao pro Seedlight: estrategias de revisao no Companion

1.3 Avaliacao e Medicao de Aprendizagem
- [x] Assessment baseado em evidencia (NRC 2001) — o triangulo da avaliacao
  - [x] Cognicao, observacao, interpretacao
  - [x] Implicacao pro Seedlight: como medir sem prova
- [x] Evidence-Centered Design (Mislevy et al.) — framework de design de avaliacao
  - [x] Modelo do aluno, modelo de tarefa, modelo de evidencia
  - [x] Implicacao pro Seedlight: arquitetura do Learner Profile
- [x] Stealth Assessment (Shute) — avaliacao invisivel
  - [x] Avaliar dentro da atividade sem a crianca perceber
  - [x] Implicacao pro Seedlight: como coletar evidencia naturalmente

**Area 6 — Equidade Algoritmica e Justica em IA**

6.1 Fundamentos de Fairness em ML
- [x] Selbst et al. (2019) — fairness e sociotecnico, 5 armadilhas de abstracao
  - [x] Framing, Portability, Formalism, Ripple Effect, Solutionism
  - [x] Mapeamento das 5 armadilhas para riscos concretos no Seedlight
  - [x] Conexao solutionism trap + SDT undermining effect
- [x] Friedler et al. (2016) — impossibilidade de fairness, definicoes mutuamente exclusivas
  - [x] Demographic parity, equal opportunity, calibration
  - [x] Implicacao pro Seedlight: equal opportunity como prioridade, falso negativo como erro critico
- [~] Barocas, Hardt & Narayanan (fairmlbook.org) — livro-texto de referencia (conceitos cobertos via Selbst + Friedler + Kizilcec; consultar se precisar de formalismos)
- [~] Cathy O'Neil — Weapons of Math Destruction — contexto nao-tecnico (coberto indiretamente; consultar pra casos narrativos)

6.2 Bias em IA Educacional
- [x] Kizilcec & Lee (2022) — fairness especifico para educacao
  - [x] Como bias se manifesta em sistemas educacionais adaptativos
  - [x] Implicacao pro Seedlight: riscos especificos do BKT e Companion
- [x] Baker & Hawn (2021) — IA em educacao amplia ou reduz desigualdade
  - [x] Survey de casos reais: quando IA educacional falhou e quando funcionou
  - [x] Implicacao pro Seedlight: licoes de sistemas anteriores
- [x] Ekowo & Palmer (2016) — modelos preditivos em educacao sem perpetuar bias
  - [x] Guia pratico para Predictive Equity
  - [x] Implicacao pro Seedlight: como construir o Equity Layer

6.3 Auditoria de Bias
- [x] Model Cards (Mitchell et al. 2019) — framework de documentacao de modelos
  - [x] O que documentar: metricas, limitacoes, bias conhecido
  - [x] Implicacao pro Seedlight: padrao de transparencia para o BKT e Companion
- [x] Datasheets for Datasets (Gebru et al. 2021) — documentacao de datasets
  - [x] Implicacao pro Seedlight: documentar dados de treinamento e calibracao
- [x] Ferramentas: Fairlearn, AIF360, Aequitas
  - [x] Metricas de fairness e algoritmos de mitigacao
  - [x] Aequitas: distincao intervencao assistiva vs punitiva, falso negativo como erro critico
  - [x] Implicacao pro Seedlight: pipeline de auditoria do Equity Layer

### Fase 2 — Hardware e Modelos Pequenos (Semanas 5-8)

**Area 5 — Modelos Pequenos e Inferencia em Dispositivos**
- [ ] 5.1 Quantizacao de Modelos
- [ ] 5.2 Modelos Candidatos para o Dispositivo
- [ ] 5.3 Treinamento com Reinforcement Learning

**Area 2 — Inteligencia Artificial para Educacao (AIED)**
- [ ] 2.1 Intelligent Tutoring Systems
- [ ] 2.2 Knowledge Tracing (BKT, DKT, SAKT, AKT)
- [ ] 2.3 Open Learner Models
- [ ] 2.4 LLMs em Educacao

### Fase 3 — Agentes, GraphRAG e Arquitetura (Semanas 9-12)

**Area 3 — Grafos de Conhecimento e Modelagem Curricular**
- [ ] 3.1 Knowledge Graphs — Fundamentos
- [ ] 3.2 Knowledge Graphs Educacionais
- [ ] 3.3 GraphRAG — Motor de Retrieval

**Area 4 — Arquitetura de Agentes com Primitivas Simples**
- [ ] 4.1 Building Effective Agents (Anthropic)
- [ ] 4.2 Memoria Persistente para o Companion
- [ ] 4.3 Retrieval no Dispositivo: GraphRAG Local
- [ ] 4.4 Estudo de Caso: OpenCode

### Fase 4 — Infra Offline e Estudos de Caso (Semanas 13-16)

**Area 7 — Privacidade de Dados e Soberania do Aprendiz**
- [ ] 7.1 Legislacao e Frameworks (LGPD, GDPR, COPPA, FERPA)
- [ ] 7.2 Privacy-Preserving ML
- [ ] 7.3 Portabilidade e Soberania Local

**Area 8 — Infraestrutura Offline-First e Edge Computing**
- [ ] 8.1 Estudo de Caso: Kolibri
- [ ] 8.2 Estudo de Caso: Project N.O.M.A.D.
- [ ] 8.3 Stack Completa de ML no Dispositivo
- [ ] 8.4 Software Offline-First (CRDTs, Automerge)
- [ ] 8.5 Raspberry Pi como Plataforma de Dev
- [ ] 8.6 Redes Mesh e Conectividade Comunitaria

**Area 9 — Padroes Abertos em Educacao**
- [ ] 9.1 Padroes Existentes (xAPI, LTI, Open Badges)
- [ ] 9.2 Protocolos de Integracao de IA (MCP, OpenAPI)

### Fase 5 — Treinamento e Integracao (Semanas 17-20)

**Area 10 — Modelagem Preditiva de Tendencias**
- [ ] 10.1 Analise de Tendencias
- [ ] 10.2 Labor Market Intelligence

**Area 11 — Design e UX para Criancas**
- [ ] 11.1 Design para Criancas
- [ ] 11.2 Interfaces para Baixa Literacia Digital
- [ ] 11.3 Visualizacao do Mapa Cognitivo

**Area 12 — Engenharia de Software e Arquitetura**
- [ ] 12.1 Arquitetura do Dispositivo Seedlight
- [ ] 12.2 Referencias de Arquitetura
- [ ] 12.3 Infraestrutura de ML

### Fase 6 — Prototipo Completo (Semanas 21-24)

- [ ] Integracao de todos os componentes
- [ ] Teste com crianca real
- [ ] Documentacao para release publico

---

## Contadores

- **Sources estudadas:** 13
- **Conceitos registrados:** 28
- **Design notes:** 32
- **Duvidas abertas:** 19
- **Conexoes no grafo:** 140

## Sessoes Recentes

- **2026-03-25** — Bloom 1984 (2 Sigma Problem). Extraido conceito central + design note mapeando mecanismos de tutoria para componentes. Sessao interrompida por crash.
- **2026-03-26** — Piaget (esquemas, assimilacao/acomodacao, estagios) + Vygotsky (ZDP, scaffolding, MKO). 7 insights registrados. Proximo: Papert.
- **2026-03-27** — Sessao 1: Revisao (Bloom+Piaget+Vygotsky) + Papert (construcionismo, microworlds, powerful ideas). Sessao 2: Revisao dos 4 autores + Lave & Wenger (cognicao situada, LPP). Area 1.1 concluida. Sessao 3: Mastery Learning (Bloom 1968) — dominio antes de avanco, aptidao como velocidade, 4 barreiras de escala. Proximo: SDT (Ryan & Deci).
- **2026-03-28** — Revisao geral (5 autores + Mastery Learning; fragil em estagios Piaget e LPP) + SDT (Ryan & Deci): 3 necessidades basicas, continuum, undermining effect, contexto sustentador vs controlador. 4 insights registrados. Proximo: Productive Failure (Kapur).
- **2026-03-29** — Sessao 1: Productive Failure (Kapur): 3 mecanismos + 3 condicoes de design, tensao suporte vs fracasso resolvida via engagement detector, BKT como decisor de tipo de instrucao. Sessao 2: Desirable Difficulties (Bjork & Bjork) — spacing, interleaving, retrieval practice, BKT com decaimento temporal. Area 1.3 completa: Triangulo NRC, ECD (Mislevy), Stealth Assessment (Shute) — evidence rules como tool do Companion, grafo pre-definido com caminho emergente. 7 insights registrados. Areas 1.1, 1.2 e 1.3 concluidas. Sessao 3: Area 6.1 (Fundamentos de Fairness em ML) — Selbst (5 armadilhas de abstracao), Friedler (impossibilidade de fairness). Equal opportunity como metrica prioritaria, engagement detector como peca de fairness, Emergent Curriculum como vetor de bias. 5 insights registrados. Proximo: Areas 6.2 e 6.3.
- **2026-03-30** — Area 6.2 completa: Kizilcec & Lee (pipeline de 4 etapas, feedback loop, representational vs historical bias), Baker & Hawn (casos reais, autonomia proporcional a confianca, fallback humano, postura conservadora), Ekowo & Palmer (Predictive Equity redefinido como expansao de horizonte). Area 6.3 completa: Model Cards (BKT Model Card com 3 factors), Datasheets for Datasets, pipeline de auditoria Aequitas → Fairlearn → AIF360. 10 concepts + 7 design notes registrados. **Fase 1 concluida.** Proximo: Fase 2.
