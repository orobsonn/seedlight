---
last-updated: 2026-03-31
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

**Area 2 — Inteligencia Artificial para Educacao (AIED)**

2.1 Intelligent Tutoring Systems (ITS)
- [x] VanLehn (2011) — meta-analise: ITS vs tutoria humana, quao perto chegam
  - [x] Implicacao pro Seedlight: o que a pesquisa ja validou sobre a premissa tecnica
- [x] Cognitive Tutors (Koedinger et al. 2007) — Carnegie Learning, ITS com resultados rigorosos em escala
  - [x] Model tracing e knowledge tracing: como o sistema rastreia o raciocinio do aluno
  - [x] Implicacao pro Seedlight: licoes de um ITS que funcionou em escala real
- [x] AutoTutor (Graesser et al. 2004) — ITS baseado em dialogo natural
  - [x] Tutoring moves: como o sistema conduz o dialogo (pumping, hints, prompts)
  - [x] Implicacao pro Seedlight: ancestral direto do que o Companion faz com LLM

2.2 Knowledge Tracing — Modelando o que o Aluno Sabe
- [x] BKT — Corbett & Anderson (1995) — o modelo original
  - [x] 4 parametros: P(L0), P(T), P(G), P(S) — o que cada um significa
  - [x] Como BKT estima probabilidade de dominio por conceito
  - [x] Implicacao pro Seedlight: motor silencioso do Learner Profile, roda em qualquer hardware
- [x] DKT — Piech et al. (2015) — deep learning entra no campo
  - [x] RNNs para knowledge tracing: vantagens e controversias
  - [x] Yeung & Yeung (2018) — correcoes ao DKT original
  - [x] Implicacao pro Seedlight: por que DKT e pesado demais pro Pi vs o que ele resolve
- [x] SAKT — Pandey & Karypis (2019) — transformers para knowledge tracing
  - [x] Self-attention para capturar dependencias entre exercicios
  - [x] Implicacao pro Seedlight: viabilidade no dispositivo vs ganho sobre BKT
- [x] AKT — Ghosh, Heffernan & Lan (2020) — estado da arte com contexto
  - [x] Atencao ao contexto: por que isso importa para aprendizagem adaptativa
  - [x] Implicacao pro Seedlight: se vale o custo computacional vs BKT no Pi 5
- [x] Panorama evolutivo: BKT → DKT → SAKT → AKT — o que cada geracao adicionou
  - [x] Trade-off complexidade vs interpretabilidade vs custo computacional
  - [x] Decisao pro Seedlight: qual modelo (ou combinacao) usar e por que

2.3 Open Learner Models
- [ ] Bull & Kay (2007) — survey fundacional: o aluno ve seu proprio modelo
  - [ ] Por que transparencia do modelo importa para metacognicao
  - [ ] Implicacao pro Seedlight: o mapa cognitivo que a crianca ve e possui
- [ ] Matcha et al. (2019) — dashboards e autorregulacao
  - [ ] Como visualizacao do progresso afeta self-regulated learning
  - [ ] Conexao com SDT: visualizacao como suporte a competencia e autonomia
  - [ ] Implicacao pro Seedlight: como apresentar o Learner Profile pra crianca
- [ ] Bodily et al. (2018) — revisao sistematica do que funciona
  - [ ] Padroes de design efetivos vs ineficazes em OLM
  - [ ] Implicacao pro Seedlight: o que evitar no design do mapa cognitivo

2.4 LLMs em Educacao — O Estado Atual
- [ ] Tack & Piech (2022) — onde LLMs funcionam e onde falham pra tutoria
  - [ ] Limites concretos: quando o dialogo do LLM ajuda e quando atrapalha
  - [ ] Implicacao pro Seedlight: como o Companion compensa as fraquezas do LLM
- [ ] Khanmigo (Khan Academy 2024) — o que o maior ITS com LLM faz
  - [ ] Arquitetura e decisoes de design do Khanmigo
  - [ ] Implicacao pro Seedlight: onde o Seedlight se diferencia fundamentalmente
- [ ] Liang et al. (2023) — limites de LLMs em avaliacao/feedback
  - [ ] O que LLMs conseguem e nao conseguem avaliar
  - [ ] Implicacao pro Seedlight: por que o LLM nao substitui o BKT pra avaliacao

**Area 5 — Modelos Pequenos e Inferencia em Dispositivos**

5.1 Quantizacao de Modelos
- [ ] Tipos de quantizacao: Q4_K_M, Q5_K_M, Q8_0
  - [ ] O que cada nivel significa: bits, trade-off tamanho/velocidade/qualidade
  - [ ] Implicacao pro Seedlight: qual nivel e viavel no Pi 5 com 8GB RAM
- [ ] Importance Matrix (imatrix) — quantizacao inteligente
  - [ ] Como identificar pesos mais importantes e preserva-los
  - [ ] Implicacao pro Seedlight: ganho de qualidade sem custo extra de hardware
- [ ] AWQ (Activation-Aware Weight Quantization) — ajuste pre-quantizacao
  - [ ] Como funciona vs quantizacao naive
- [ ] Formato GGUF — o padrao do ecossistema local
  - [ ] Estrutura, extensibilidade, por que substituiu GGML
  - [ ] Implicacao pro Seedlight: formato de distribuicao dos modelos no dispositivo
- [ ] llama.cpp — inferencia em C/C++ puro
  - [ ] Build system, benchmark tools, server mode, embedding generation
  - [ ] Implicacao pro Seedlight: motor de inferencia do dispositivo

5.2 Modelos Candidatos para o Dispositivo
- [ ] Qwen 2.5 / Qwen 3 (1.5B) — capacidade de raciocinio, multilingue
- [ ] Llama 3.2 (1B / 3B) — familia Meta, ultracompacto vs mais capaz
- [ ] SmolLM2 (1.7B) — HuggingFace, eficiencia como foco
- [ ] Phi-4-mini (3.8B) — Microsoft, forte em raciocinio, possivel limite de hardware
- [ ] Granite 4.0 Micro — IBM, edge computing, tool use nativo
- [ ] Benchmark comparativo no Pi 5
  - [ ] Metricas: tok/s, qualidade em portugues, consumo RAM, consumo energia
  - [ ] Implicacao pro Seedlight: decisao informada de qual modelo usar

5.3 Treinamento com Reinforcement Learning
- [ ] DeepSeek-R1 (2025) — RL ensina modelos a raciocinar
  - [ ] Como GRPO funciona: sem value model, economia de memoria
  - [ ] Por que GRPO e melhor que PPO pro Seedlight
- [ ] DeepResearcher (Zheng et al. 2025) — RL end-to-end em ambientes reais
  - [ ] Metodologia: como 7B treinado com RL supera modelos maiores
  - [ ] Implicacao pro Seedlight: treinar 1.5B pra ser excepcional em tutoria
- [ ] Search-R1 — RL pra buscar e raciocinar
  - [ ] Tecnica aplicavel ao Companion buscando no curriculum graph
- [ ] Pipeline de treinamento: base → SFT → RL
  - [ ] SFT com dialogos educacionais de qualidade
  - [ ] Reward functions pedagogicas: compreensao, nivel adequado, motivacao
  - [ ] Viabilidade: 1.5B + GRPO + LoRA em 1x RTX 4090
  - [ ] Implicacao pro Seedlight: o caminho de modelo generico a tutor especializado

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

- **Sources estudadas:** 16
- **Conceitos registrados:** 36
- **Design notes:** 35
- **Duvidas abertas:** 21
- **Conexoes no grafo:** 162

## Sessoes Recentes

- **2026-03-25** — Bloom 1984 (2 Sigma Problem). Extraido conceito central + design note mapeando mecanismos de tutoria para componentes. Sessao interrompida por crash.
- **2026-03-26** — Piaget (esquemas, assimilacao/acomodacao, estagios) + Vygotsky (ZDP, scaffolding, MKO). 7 insights registrados. Proximo: Papert.
- **2026-03-27** — Sessao 1: Revisao (Bloom+Piaget+Vygotsky) + Papert (construcionismo, microworlds, powerful ideas). Sessao 2: Revisao dos 4 autores + Lave & Wenger (cognicao situada, LPP). Area 1.1 concluida. Sessao 3: Mastery Learning (Bloom 1968) — dominio antes de avanco, aptidao como velocidade, 4 barreiras de escala. Proximo: SDT (Ryan & Deci).
- **2026-03-28** — Revisao geral (5 autores + Mastery Learning; fragil em estagios Piaget e LPP) + SDT (Ryan & Deci): 3 necessidades basicas, continuum, undermining effect, contexto sustentador vs controlador. 4 insights registrados. Proximo: Productive Failure (Kapur).
- **2026-03-29** — Sessao 1: Productive Failure (Kapur): 3 mecanismos + 3 condicoes de design, tensao suporte vs fracasso resolvida via engagement detector, BKT como decisor de tipo de instrucao. Sessao 2: Desirable Difficulties (Bjork & Bjork) — spacing, interleaving, retrieval practice, BKT com decaimento temporal. Area 1.3 completa: Triangulo NRC, ECD (Mislevy), Stealth Assessment (Shute) — evidence rules como tool do Companion, grafo pre-definido com caminho emergente. 7 insights registrados. Areas 1.1, 1.2 e 1.3 concluidas. Sessao 3: Area 6.1 (Fundamentos de Fairness em ML) — Selbst (5 armadilhas de abstracao), Friedler (impossibilidade de fairness). Equal opportunity como metrica prioritaria, engagement detector como peca de fairness, Emergent Curriculum como vetor de bias. 5 insights registrados. Proximo: Areas 6.2 e 6.3.
- **2026-03-30** — Area 6.2 completa: Kizilcec & Lee (pipeline de 4 etapas, feedback loop, representational vs historical bias), Baker & Hawn (casos reais, autonomia proporcional a confianca, fallback humano, postura conservadora), Ekowo & Palmer (Predictive Equity redefinido como expansao de horizonte). Area 6.3 completa: Model Cards (BKT Model Card com 3 factors), Datasheets for Datasets, pipeline de auditoria Aequitas → Fairlearn → AIF360. 10 concepts + 7 design notes registrados. **Fase 1 concluida.** Proximo: Fase 2.
- **2026-03-31** — Area 2.1 completa: VanLehn (ITS d=0.76 ≈ humano d=0.79, step-level feedback e decisivo), Koedinger (Cognitive Tutors, model tracing), Graesser (AutoTutor, tutoring moves). Padrao estrategista-executor: harness decide, LLM executa. Area 2.2 completa: BKT mecanica (4 parametros), evolucao BKT→DKT→SAKT→AKT (trade-off capacidade vs interpretabilidade), BKT+GraphRAG como solucao arquitetural. Discussao sobre pipeline SLM especializado (distillation+SFT+RL) e reavaliacao de premissas offline. 8 concepts + 3 design notes registrados. Proximo: Areas 2.3 e 2.4.
