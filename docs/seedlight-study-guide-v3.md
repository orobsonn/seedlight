# Seedlight — Guia de Estudos Fundamentais v3

*Um mapa de conhecimento para construir algo sério.*

> Este documento organiza tudo que você precisa estudar para construir o Seedlight com profundidade técnica e teórica. Cada área macro contém os conceitos fundamentais, os papers seminais, e os repositórios de referência. A ordem importa — comece pela Área 1 e avance sequencialmente.
>
> **v3 — Atualizado** com GraphRAG como motor de retrieval (substituindo Vector RAG), Project N.O.M.A.D. e OpenCode como estudos de caso arquiteturais, e a stack completa de ML que roda no dispositivo. O Seedlight será construído com LLM no dispositivo da criança desde o início, sem dependência de internet ou hub escolar. Frameworks pesados foram descartados em favor de composable patterns com primitivas simples.

---

## Área 1 — Ciências da Aprendizagem

**Por que isso vem primeiro:** Você está construindo um sistema educacional. Se não entender profundamente como seres humanos aprendem, vai construir tecnologia que impressiona engenheiros e falha com crianças. Esta é a fundação de tudo.

### 1.1 Teorias Fundamentais de Aprendizagem

Antes de qualquer linha de código, você precisa entender as três grandes tradições que fundamentam o que o Seedlight propõe.

**Construtivismo (Piaget)** — A ideia de que conhecimento não é transmitido, é construído pelo aprendiz através da interação com o mundo. Isso é a base filosófica do Emergent Curriculum.

**Zona de Desenvolvimento Proximal (Vygotsky)** — O conceito de que existe uma faixa entre o que a criança consegue fazer sozinha e o que consegue fazer com ajuda. O Longitudinal Companion precisa operar exatamente nessa faixa.

**Construcionismo (Seymour Papert)** — A evolução de Piaget: aprender fazendo, especialmente fazendo coisas significativas para o aprendiz. Papert criou o Logo e fundou o MIT Media Lab pensando exatamente nisso.

#### Papers e Livros Fundamentais

- **"Mindstorms: Children, Computers, and Powerful Ideas"** — Seymour Papert (1980). Livro obrigatório. Escrito há mais de 40 anos, descreve essencialmente o que o Seedlight quer fazer. Se você ler um único livro, que seja este.

- **"How People Learn: Brain, Mind, Experience, and School"** — National Research Council (2000). Síntese definitiva de como aprendizagem funciona. Disponível gratuitamente no site da National Academies Press.

- **"How People Learn II: Learners, Contexts, and Cultures"** — National Academies (2018). Atualização do anterior, com ênfase em contexto cultural e equidade — diretamente relevante para o Layer 3 do Seedlight.

- **"The 2 Sigma Problem: The Search for Methods of Group Instruction as Effective as One-to-One Tutoring"** — Benjamin Bloom (1984). O paper que demonstrou que tutoria individual produz resultados 2 desvios-padrão acima da instrução em grupo. Este é o "porquê" estatístico do Seedlight.

- **"Situated Learning: Legitimate Peripheral Participation"** — Lave & Wenger (1991). A teoria de que aprendizagem acontece em contexto, não em abstração. Fundamenta diretamente o Context Adapter do Seedlight.

### 1.2 Aprendizagem Adaptativa e Personalizada

O Seedlight promete adaptação contínua. Você precisa entender o que já se sabe sobre isso e o que funciona de verdade versus o que é marketing.

#### Papers Fundamentais

- **"Mastery Learning"** — Bloom (1968). O conceito de que todos podem aprender se tiverem tempo e instrução adequados. Fundamenta o pacing adaptativo do Emergent Curriculum.

- **"Self-Determination Theory and the Facilitation of Intrinsic Motivation, Social Development, and Well-Being"** — Ryan & Deci (2000). A teoria dominante sobre motivação intrínseca. Você precisa entender isso porque o Seedlight propõe substituir motivação extrínseca (notas) por intrínseca (conexão com a vida real).

- **"Productive Failure"** — Kapur (2008, 2016). Demonstra que o fracasso estruturado durante a aprendizagem produz compreensão mais profunda. Relevante para como o Companion deve calibrar desafios.

- **"Desirable Difficulties in Learning"** — Bjork & Bjork (2011). Nem toda dificuldade atrapalha — algumas melhoram a retenção. O sistema precisa distinguir entre frustração produtiva e improdutiva.

### 1.3 Avaliação e Medição de Aprendizagem

O Seedlight propõe avaliação contínua e contextual. Você precisa entender o que isso significa tecnicamente.

#### Papers Fundamentais

- **"Knowing What Students Know: The Science and Design of Educational Assessment"** — NRC (2001). Framework completo de avaliação educacional baseada em evidência.

- **"Evidence-Centered Design"** — Mislevy, Almond & Lukas (2003). O framework padrão para design de avaliação. Relevante para como o Learner Profile Engine mede compreensão.

- **"Stealth Assessment"** — Valerie Shute (2011). Avaliação embutida na atividade de aprendizagem sem que o aluno perceba que está sendo avaliado. Exatamente o que o Seedlight precisa implementar.

---

## Área 2 — Inteligência Artificial para Educação (AIED)

**Por que esta área existe:** O campo de AI in Education tem 50+ anos de pesquisa. Ignorar isso e construir do zero seria arrogância e desperdício. Muitas das ideias do Seedlight já foram tentadas em formas mais limitadas — você precisa saber o que funcionou e o que não funcionou.

### 2.1 Intelligent Tutoring Systems (ITS)

Os ITS são os ancestrais diretos do que o Seedlight propõe. Estudá-los evita que você reinvente a roda.

#### Papers Fundamentais

- **"The Relative Effectiveness of Human Tutoring, Intelligent Tutoring Systems, and Other Tutoring Systems"** — VanLehn (2011). Meta-análise definitiva comparando tutoria humana, ITS e outras abordagens. Resultado: ITS chegam perto da tutoria humana. Isso valida a premissa técnica do Seedlight.

- **"Cognitive Tutors: Technology Bringing Learning Sciences to the Classroom"** — Koedinger et al. (2007). O sistema Carnegie Learning / Cognitive Tutor, um dos poucos ITS que produziu resultados rigorosos em escala real.

- **"AutoTutor: An Intelligent Tutoring System with Mixed-Initiative Dialogue"** — Graesser et al. (2004). Um dos primeiros ITS baseados em diálogo natural. Ancestral direto do que LLMs permitem hoje.

### 2.2 Knowledge Tracing — Modelando o que o Aluno Sabe

O Learner Profile Engine do Seedlight é essencialmente um sistema de Knowledge Tracing avançado. Esta é a área técnica mais diretamente relevante. Knowledge tracing é IA tradicional (não generativa) — leve, eficiente, roda em qualquer hardware. É o motor silencioso que funciona no dispositivo mesmo quando o LLM está ocioso.

#### Papers Fundamentais (em ordem cronológica — a evolução importa)

- **"Knowledge Tracing: Modeling the Acquisition of Procedural Knowledge"** — Corbett & Anderson (1995). O paper original de Bayesian Knowledge Tracing (BKT). Modelo simples mas poderoso que rastreia probabilidade de domínio por conceito. Você precisa entender isso profundamente.

- **"Deep Knowledge Tracing"** — Piech et al. (2015). Aplicação de RNNs para knowledge tracing. Marcou a entrada de deep learning no campo. Resultados controversos mas influentes.

- **"Addressing Two Problems in Deep Knowledge Tracing via Prediction-Consistent Regularization"** — Yeung & Yeung (2018). Correções aos problemas do DKT original.

- **"A Self-Attentive Model for Knowledge Tracing"** (SAKT) — Pandey & Karypis (2019). Aplicação de transformers para knowledge tracing. Arquitetura mais moderna.

- **"Context-Aware Attentive Knowledge Tracing"** (AKT) — Ghosh, Heffernan & Lan (2020). Estado da arte em knowledge tracing com atenção a contexto. Diretamente relevante para o Seedlight.

#### Repositórios de Referência

- **pyBKT** — github.com/CAHLR/pyBKT — Implementação Python de Bayesian Knowledge Tracing. Comece por aqui para entender a mecânica. BKT é leve o suficiente para rodar em qualquer dispositivo.

- **XKT** — github.com/ai4ed/XKT — Coleção de modelos de knowledge tracing (BKT, DKT, SAKT, AKT). Boa base comparativa.

- **EduData** — github.com/bigdata-ustc/EduData — Datasets educacionais para treinar e testar modelos. Inclui ASSISTments, Junyi Academy, etc.

### 2.3 Open Learner Models

O Seedlight propõe que o aluno veja e possua seu próprio mapa cognitivo. Isso é um campo de pesquisa chamado Open Learner Models.

#### Papers Fundamentais

- **"Open Learner Models: Research Questions"** — Bull & Kay (2007). Survey fundacional do campo.

- **"Scaffolding Self-Regulated Learning Through Student-Facing Learning Analytics Dashboards"** — Matcha et al. (2019). Como visualizações do progresso do aluno afetam autorregulação.

- **"Open Learner Models and Learning Analytics Dashboards: A Systematic Review"** — Bodily et al. (2018). Revisão sistemática do que funciona.

### 2.4 LLMs em Educação — O Estado Atual

Você precisa saber o que já está sendo feito com LLMs em educação para entender onde o Seedlight se diferencia.

#### Papers Fundamentais

- **"Opportunities and Challenges in Neural Dialog Tutoring"** — Tack & Piech (2022). Análise honesta de onde LLMs funcionam e onde falham para tutoria.

- **"Sparks of Artificial General Intelligence"** — Bubeck et al. (2023). Não é educacional, mas demonstra as capacidades de raciocínio que o Seedlight precisa dos LLMs.

- **"Can Large Language Models Provide Useful Feedback on Research Papers?"** — Liang et al. (2023). Relevante para entender limites de LLMs em avaliação.

- **"Khanmigo Technical Report"** — Khan Academy (2024). Documentação técnica do Khanmigo. O Seedlight se posiciona como fundamentalmente diferente, então você precisa entender profundamente o que o Khanmigo faz.

---

## Área 3 — Grafos de Conhecimento e Modelagem Curricular

**Por que isso importa:** O Curriculum Graph é um dos componentes centrais do Seedlight. Ele precisa representar conhecimento de forma flexível, com múltiplos pontos de entrada contextuais. Isso não é trivial. E precisa ser armazenável localmente no dispositivo.

### 3.1 Knowledge Graphs — Fundamentos

#### Papers Fundamentais

- **"Knowledge Graphs"** — Hogan et al. (2021). Survey abrangente e recente. Leitura densa mas necessária para entender o campo.

- **"Representation Learning on Graphs: Methods and Applications"** — Hamilton, Ying & Leskovec (2017). Como aprender representações vetoriais de nós em grafos — essencial para busca de similaridade no curriculum graph.

### 3.2 Knowledge Graphs Educacionais

#### Papers Fundamentais

- **"Knowledge Tracing Machines: Factorization Machines for Knowledge Tracing"** — Vie & Kashima (2019). Conexão entre grafos de conhecimento e knowledge tracing.

- **"Prerequisite Relation Learning for Concepts in MOOCs"** — Pan et al. (2017). Como modelar relações de pré-requisito entre conceitos — fundamental para o pacing adaptativo.

- **"Concept Prerequisite Learning Using Multi-Head Attention"** — Roy et al. (2019). Abordagem mais recente usando attention.

### 3.3 GraphRAG — O Motor de Retrieval do Seedlight

Esta é uma das seções mais críticas do guia. O Seedlight NÃO usa Vector RAG convencional (busca por similaridade de texto). Usa GraphRAG — recuperação baseada em travessia de grafos de conhecimento. A diferença é fundamental: Vector RAG pergunta "que texto é parecido com a pergunta?". GraphRAG pergunta "que entidades estão conectadas a esta situação, e como?"

Para o Seedlight, isso significa que quando o Companion precisa decidir o próximo passo pedagógico, ele não busca chunks de texto — ele atravessa o grafo de conceitos, relações de pré-requisito, contextos que funcionam para aquela criança, e estados de domínio. Isso permite multi-hop reasoning: combinar informações de múltiplas fontes conectadas para derivar respostas através de conexões lógicas.

#### Papers Fundamentais

- **"Retrieval-Augmented Generation with Graphs (GraphRAG)"** — Han et al. (2025, arXiv:2501.00309). Survey abrangente e atualizado de GraphRAG. Cobre taxonomia, mecanismos, desafios e implementações. Leitura obrigatória para entender o campo completo.

- **"From Local to Global: A Graph RAG Approach to Query-Focused Summarization"** — Edge et al. (2024, Microsoft Research). O paper da Microsoft que popularizou o termo GraphRAG. Demonstra como extrair knowledge graphs de corpus textual e usar comunidades de grafos para responder perguntas complexas.

- **"Document GraphRAG: Knowledge Graph Enhanced Retrieval Augmented Generation"** — (2025, MDPI Electronics). Demonstra ganhos consistentes sobre RAG convencional em retrieval e geração, usando grafos construídos a partir da estrutura intrínseca dos documentos.

- **"Improving Retrieval Augmented Generation accuracy with GraphRAG"** — AWS/Lettria (2024). Demonstra melhoria de até 35% na precisão de respostas com GraphRAG vs. Vector RAG. Dados concretos para justificar a decisão arquitetural.

#### Repositórios de Referência

- **Microsoft GraphRAG** — github.com/microsoft/graphrag — A implementação de referência da Microsoft. Pipeline completo: extração de entidades/relações → construção do grafo → detecção de comunidades → geração de summaries → query. Pesado demais para rodar no dispositivo como está, mas a arquitetura conceitual é o que importa estudar.

- **nano-graphrag** — github.com/gusye1234/nano-graphrag — Implementação leve e simples de GraphRAG. Muito mais adequado como ponto de partida para adaptar ao dispositivo Seedlight.

- **LightRAG** — github.com/HKUDS/LightRAG — RAG com grafos otimizado para eficiência. Candidato a adaptação para edge computing.

- **MiniRAG** — github.com/HKUDS/MiniRAG — Do mesmo time do LightRAG, desenhado especificamente para SLMs (modelos de 1.5B parâmetros). Usa apenas 25% do armazenamento do RAG tradicional. Grafo heterogêneo que combina chunks de texto + entidades nomeadas. Precisão cai apenas 0.8%-20% vs LLMs completos. Candidato forte para o dispositivo Seedlight.

#### Desafio Técnico: GraphRAG no Dispositivo

O Microsoft GraphRAG original foi desenhado para rodar em servidores potentes. O Seedlight precisa de uma versão que rode num Raspberry Pi. Isso significa: grafo pré-construído e armazenado em SQLite (não construído on-the-fly), travessia de grafo com algoritmos leves (BFS/DFS limitado, não community detection em tempo real), embeddings gerados localmente via llama.cpp, e cache agressivo de sub-grafos frequentemente acessados. Isso é engenharia nova — não existe referência pronta. É onde o Seedlight inova.

#### Repositórios de Armazenamento Local

- **SQLite** — sqlite.org — O grafo de conceitos será modelado em SQLite com tabelas de nós, arestas e propriedades. Sem necessidade de Neo4j no dispositivo.

- **sqlite-vec** — github.com/asg017/sqlite-vec — Extensão para busca vetorial em SQLite, sucessor do sqlite-vss (deprecated). C puro, zero dependências, roda em qualquer plataforma onde SQLite roda (incluindo Raspberry Pi Zero). Suporta bit vectors para redução de 32x no espaço. Para o currículo escolar (~500-2000 conceitos), busca brute-force é instantânea.

- **NetworkX** — github.com/networkx/networkx — Para prototipagem e validação de algoritmos de travessia do grafo curricular.

---

## Área 4 — Arquitetura de Agentes com Primitivas Simples

**Por que isso importa:** O Longitudinal Companion é um agente LLM com memória e ferramentas. Mas a decisão arquitetural do Seedlight é construí-lo SEM frameworks pesados como CrewAI ou LangGraph, seguindo a filosofia da Anthropic de composable patterns. Isso dá controle total, elimina dependências frágeis, e é essencial para um sistema que precisa rodar em hardware limitado.

### 4.1 A Filosofia: Building Effective Agents (Anthropic)

#### Leituras Obrigatórias

- **"Building Effective Agents"** — Blog Anthropic (Dez 2024). O documento fundacional. Mensagem central: comece com a solução mais simples possível, só aumente complexidade quando necessário. Define a distinção entre workflows (caminhos predefinidos) e agents (LLM direciona o processo). Apresenta composable patterns: prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer.
  - URL: anthropic.com/research/building-effective-agents

- **"Effective Context Engineering for AI Agents"** — Blog Anthropic (2025). A evolução natural do post anterior. Context engineering como a disciplina central de construção de agentes. Ensina a tratar contexto como recurso finito e precioso — crítico para modelos pequenos onde cada token conta.
  - URL: anthropic.com/engineering/effective-context-engineering-for-ai-agents

- **"Writing Effective Tools for AI Agents"** — Blog Anthropic (2025). Como projetar ferramentas que agentes conseguem usar de forma confiável. Ferramentas são contratos entre sistemas determinísticos e agentes não-determinísticos.
  - URL: anthropic.com/engineering/writing-tools-for-agents

- **"Demystifying Evals for AI Agents"** — Blog Anthropic (2026). Como avaliar agentes rigorosamente. Eval-driven development: construa avaliações antes de construir funcionalidades.
  - URL: anthropic.com/engineering/demystifying-evals-for-ai-agents

### 4.2 Memória Persistente para o Companion

O Companion precisa acumular conhecimento sobre o aprendiz ao longo de meses e anos — tudo armazenado localmente no dispositivo.

#### Papers Fundamentais

- **"MemGPT: Towards LLMs as Operating Systems"** — Packer et al. (2023). Gerenciamento hierárquico de memória para LLMs inspirado em sistemas operacionais. A analogia memória principal / memória virtual é diretamente aplicável: o contexto ativo do LLM é a RAM, o perfil completo do aprendiz no SQLite é o disco.

- **"Generative Agents: Interactive Simulacra of Human Behavior"** — Park et al. (2023). Demonstra como memória estruturada + reflexão + planejamento criam comportamento coerente a longo prazo.

- **"Reflexion: Language Agents with Verbal Reinforcement Learning"** — Shinn et al. (2023). Agentes que aprendem com suas próprias reflexões. Relevante para o Companion evoluir sua compreensão do aprendiz.

#### Repositórios de Referência

- **Letta (ex-MemGPT)** — github.com/letta-ai/letta — Estudar a arquitetura de memória, não usar como dependência. Entender como eles resolvem o problema de contexto limitado com memória hierárquica.

- **Mem0** — github.com/mem0ai/mem0 — Camada de memória para LLMs. Estudar como referência, implementar própria versão leve para o dispositivo.

### 4.3 Retrieval no Dispositivo: GraphRAG Local

O Companion precisa recuperar informações relevantes do histórico do aprendiz e do curriculum graph. A estratégia de retrieval do Seedlight é GraphRAG local (ver Área 3.3 para fundamentos teóricos). Na prática, o fluxo é: query do Companion → travessia do grafo em SQLite para encontrar conceitos/relações relevantes → busca vetorial complementar em SQLite VSS → montagem do contexto → envio ao LLM.

#### Papers Fundamentais

- **"Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks"** — Lewis et al. (2020). O paper original de RAG. Entender a base antes de entender a evolução.

- **"Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection"** — Asai et al. (2023). RAG com auto-reflexão — relevante para o Companion decidir quando buscar contexto histórico vs. quando já tem informação suficiente. Crítico para economia de tokens em modelos pequenos.

### 4.4 Estudo de Caso Arquitetural: OpenCode

O OpenCode não é para copiar, é para estudar padrões de engenharia que se aplicam diretamente ao Seedlight. É um agente de coding open-source escrito em Go com arquitetura limpa e bem documentada.

#### Repositórios

- **github.com/sst/opencode** — O repo principal (by SST/Anomaly). Este é o que está em desenvolvimento ativo com 120k+ stars.
- **github.com/opencode-ai/opencode** — O repo original em Go. Mais simples, bom para entender a base.

#### O que estudar no código-fonte

- **Arquitetura cliente/servidor** — separação entre o "cérebro" (que roda o LLM) e a interface do usuário. No Seedlight, o "cérebro" roda no mesmo dispositivo, mas a separação de responsabilidades é a mesma. O OpenCode foi desenhado para que o TUI seja apenas um dos possíveis clientes — exatamente o padrão que precisamos.

- **Gerenciamento de sessões com SQLite** — como o OpenCode persiste conversas e contexto entre sessões. Diretamente aplicável ao perfil longitudinal do aprendiz.

- **Agnosticismo de provedor** — como o OpenCode suporta múltiplos LLMs (Claude, OpenAI, Gemini, modelos locais) com a mesma interface. O Seedlight precisa funcionar com qualquer modelo pequeno disponível.

- **Auto-compact de contexto** — como o OpenCode automaticamente resume conversas quando se aproxima do limite de contexto do modelo. Crítico para modelos pequenos com janela de contexto limitada.

- **Integração com MCP** — Model Context Protocol como forma padrão de conectar ferramentas ao agente. Estudar como eles definem e registram MCP servers.

- **Sistema de agentes (build/plan)** — dois agentes com perfis diferentes que o usuário alterna. No Seedlight, poderíamos ter agentes para diferentes modos (ensino, avaliação, exploração livre).

---

## Área 5 — Modelos Pequenos e Inferência em Dispositivos de Baixo Custo

**Por que isso importa:** Esta é a área mais definidora da viabilidade do Seedlight. A decisão de colocar o LLM no dispositivo da criança significa que você precisa dominar inferência eficiente em hardware limitado. Este conhecimento é o que separa o Seedlight de um projeto de laboratório de uma solução real.

### 5.1 Quantização de Modelos

Quantização é o que torna possível rodar modelos grandes em hardware pequeno — reduzindo a precisão dos pesos (de 32-bit para 4-bit, por exemplo) com perda mínima de qualidade.

#### Conceitos que você precisa dominar

- **Tipos de quantização**: Q4_K_M, Q5_K_M, Q8_0 — o que cada um significa, trade-offs entre tamanho/velocidade/qualidade.
- **Importance matrix (imatrix)**: técnica para identificar quais pesos são mais importantes e quantizá-los com menos perda.
- **AWQ (Activation-Aware Weight Quantization)**: ajusta pesos antes da quantização para minimizar erro.
- **Formato GGUF**: o formato padrão para modelos quantizados — extensível, self-contained, futuro do ecossistema local.

#### Repositórios de Referência

- **llama.cpp** — github.com/ggml-org/llama.cpp — O repositório mais importante desta seção inteira. Inferência de LLMs em C/C++ puro, sem dependências. Suporta quantização de 1.5-bit a 8-bit. Roda em ARM (Raspberry Pi, smartphones). Expõe API compatível com OpenAI. Estude a fundo: build system, benchmark tools, server mode, embedding generation.

- **Ollama** — github.com/ollama/ollama — Wrapper amigável para llama.cpp. Facilita gerenciar e rodar modelos locais. Útil para prototipagem rápida no Pi.

### 5.2 Modelos Candidatos para o Dispositivo

Modelos sub-3B que são candidatos realistas para rodar no dispositivo Seedlight:

- **Qwen 2.5 1.5B / Qwen 3 1.5B** — Excelente capacidade de raciocínio para o tamanho. Multilíngue, incluindo português. Candidato forte.

- **Llama 3.2 1B / 3B** — A família Meta. O 1B é ultracompacto (~1GB quantizado). O 3B é mais capaz mas exige mais RAM.

- **SmolLM2 1.7B** — Treinado pela Hugging Face especificamente para ser eficiente. Boa opção de baseline.

- **Phi-4-mini 3.8B** — Microsoft. Forte em raciocínio, treinado com dados sintéticos de alta qualidade. Pode ser grande demais para os dispositivos mais limitados.

- **Granite 4.0 Micro** — IBM. Desenhado para edge computing, Apache 2.0, bom para agentes com tools.

#### Atividade Prática Essencial

Compre um Raspberry Pi 5 (8GB). Instale Ollama. Baixe cada um desses modelos em Q4_K_M. Teste: velocidade de geração (tokens/segundo), qualidade de respostas para diálogos educacionais em português, consumo de memória, consumo de energia com bateria. Documente tudo. Esse benchmark vai informar qual modelo usar.

### 5.3 Treinamento de Modelos Especializados com Reinforcement Learning

Esta é a fronteira que pode transformar o Seedlight. Um modelo genérico de 1.5B é bom. Um modelo de 1.5B treinado especificamente para tutoria educacional pode ser extraordinário para o seu tamanho.

#### Papers Fundamentais

- **"DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-world Environments"** — Zheng et al. (2025). O paper que demonstra que um modelo 7B treinado com RL end-to-end em ambientes reais supera baselines muito maiores. A metodologia é aplicável ao Seedlight: treinar um modelo pequeno com RL em interações educacionais reais.

- **"DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning"** — DeepSeek (2025). O paper que mostrou ao mundo que RL pode ensinar modelos a raciocinar. Inspiração direta para o DeepResearcher e para o Seedlight.

- **"Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning"** — Paper que treina LLMs com RL para buscar e raciocinar. Técnica aplicável ao Companion aprender a buscar no curriculum graph.

#### Repositórios de Referência

- **GAIR-NLP/DeepResearcher** — github.com/GAIR-NLP/DeepResearcher — Framework completo de treinamento de agentes com RL em ambientes reais. Baseado no veRL. Estudar a fundo: como eles definem rewards, como escalam o treinamento, como lidam com os desafios técnicos de RL em ambientes reais.

- **veRL** — O framework de RL para LLMs usado pelo DeepResearcher. Suporta GRPO, PPO, e outros algoritmos. Compatível com Hugging Face Transformers. **Nota: GRPO (Group Relative Policy Optimization) é o algoritmo recomendado para o Seedlight** — não precisa de value model separado, economizando ~30-40% de memória GPU vs PPO. Com GRPO, treinar um modelo de 1.5B é viável em 1x RTX 4090 com LoRA.

- **Tongyi DeepResearch** — github (buscar "tongyi-agent") — Outro framework aberto que vai do pré-treinamento agêntico ao SFT ao RL, com modelo 30B-A3B (Mixture of Experts). Interessante por demonstrar o pipeline completo de treinamento.

#### Visão para o Seedlight

O caminho seria: pegar um modelo base pequeno (Qwen 1.5B ou similar) → fazer SFT (supervised fine-tuning) com dados de diálogos educacionais de qualidade → treinar com RL usando recompensas baseadas em métricas pedagógicas (o aluno entendeu o conceito? a explicação estava no nível certo? a motivação aumentou?). Isso produz um modelo que não é genericamente inteligente, mas é excepcionalmente bom em ensinar.

---

## Área 6 — Equidade Algorítmica e Justiça em IA

**Por que isso importa:** O Layer 3 (Predictive Equity) é a parte mais ambiciosa e mais perigosa do Seedlight. Se construído de forma ingênua, automatiza injustiça. Não existe atalho aqui — você precisa entender profundamente o campo de fairness em ML.

### 6.1 Fundamentos de Fairness em Machine Learning

#### Papers Fundamentais

- **"Fairness and Abstraction in Sociotechnical Systems"** — Selbst et al. (2019). O paper mais importante desta lista. Demonstra como "fairness" é um conceito sociotécnico que não pode ser resolvido apenas com matemática. Leitura obrigatória antes de qualquer design do Equity Layer.

- **"On the (im)possibility of fairness"** — Friedler, Scheidegger & Venkatasubramanian (2016). Demonstração matemática de que diferentes definições de fairness são mutuamente exclusivas. Implicação: o Seedlight terá que fazer escolhas explícitas.

- **"Fairness and Machine Learning: Limitations and Opportunities"** — Barocas, Hardt & Narayanan. Livro-texto completo sobre fairness em ML, disponível gratuitamente em fairmlbook.org.

- **"Weapons of Math Destruction"** — Cathy O'Neil (2016). Livro acessível sobre como algoritmos perpetuam desigualdade. Não é técnico mas contextualiza o risco.

### 6.2 Bias em IA Educacional

#### Papers Fundamentais

- **"Algorithmic Fairness in Education"** — Kizilcec & Lee (2022). Específico para o contexto educacional. Diretamente relevante.

- **"Equity and Artificial Intelligence in Education"** — Baker & Hawn (2021). Survey de como IA em educação pode ampliar ou reduzir desigualdade.

- **"Ensuring Equity in Predictive Analytics for Student Success"** — Ekowo & Palmer (2016). Guia prático para como construir modelos preditivos em educação sem perpetuar bias.

### 6.3 Auditoria de Bias

O Seedlight se compromete com auditoria pública de bias. Você precisa saber como isso se faz.

#### Papers e Ferramentas Fundamentais

- **"Model Cards for Model Reporting"** — Mitchell et al. (2019). Framework de documentação de modelos que inclui análise de bias. O padrão que o Seedlight deveria adotar.

- **"Datasheets for Datasets"** — Gebru et al. (2021). Framework análogo para documentação de datasets.

#### Repositórios de Referência

- **Fairlearn** — github.com/fairlearn/fairlearn — Toolkit Microsoft para avaliação e mitigação de fairness em ML.

- **AI Fairness 360** — github.com/Trusted-AI/AIF360 — Toolkit IBM com métricas de fairness e algoritmos de mitigação.

- **Aequitas** — github.com/dssg/aequitas — Ferramenta de auditoria de bias do Data Science for Social Good. **Insight chave para o Seedlight:** Aequitas formaliza a distinção entre intervenções assistivas (educação) e punitivas (justiça criminal). Em educação, onde o sistema AJUDA crianças, o erro mais grave é o **falso negativo** — não identificar uma criança que precisa de apoio. Isso é fundamentalmente diferente de outros domínios e deve guiar a escolha de métricas de fairness.

---

## Área 7 — Privacidade de Dados e Soberania do Aprendiz

**Por que isso importa:** O Seedlight lida com dados sensíveis de crianças acumulados ao longo de anos. Com o modelo de dispositivo autossuficiente, os dados vivem no dispositivo da criança — o que é ótimo para privacidade, mas exige design cuidadoso para backup, portabilidade e segurança.

### 7.1 Legislação e Frameworks de Privacidade

- **LGPD (Lei Geral de Proteção de Dados)** — Lei brasileira. Atenção especial ao Art. 14 sobre dados de menores.
- **GDPR** — Regulamento europeu. Atenção ao "right to be forgotten" e portabilidade.
- **COPPA** — Lei americana para dados de crianças online.
- **FERPA** — Lei americana sobre registros educacionais.

### 7.2 Privacy-Preserving Machine Learning

Relevante especialmente se/quando dados agregados e anonimizados forem usados para treinar modelos melhores ou alimentar o Equity Layer.

#### Papers Fundamentais

- **"Deep Learning with Differential Privacy"** — Abadi et al. (2016). Como treinar modelos preservando privacidade individual.

- **"Communication-Efficient Learning of Deep Networks from Decentralized Data"** — McMahan et al. (2017). O paper original de Federated Learning. Permite que modelos melhorem aprendendo de dados distribuídos nos dispositivos sem centralizar informações pessoais.

#### Repositórios de Referência

- **Flower** — github.com/adap/flower — Framework de Federated Learning maduro e acessível.
- **Opacus** — github.com/pytorch/opacus — Differential Privacy para PyTorch.

### 7.3 Portabilidade e Soberania Local

- **Solid Project** — solidproject.org — Dados pessoais descentralizados, controlados pelo usuário. Filosoficamente alinhado com o Seedlight.
- **Verifiable Credentials (W3C)** — Credenciais verificáveis portáveis. Para o aprendiz provar competências.
- **Open Badges (1EdTech)** — Micro-credenciais digitais abertas.

---

## Área 8 — Infraestrutura Offline-First e Edge Computing

**Por que isso importa:** Esta área não existia na v1 do guia. Ela existe agora porque a decisão de colocar o LLM no dispositivo e funcionar sem internet é a decisão arquitetural mais definidora do projeto. Tudo aqui é novo território e é o que torna o Seedlight possível nos contextos que ele promete atingir.

### 8.1 Estudo de Caso Obrigatório: Kolibri

Antes de construir qualquer coisa, estude o Kolibri da Learning Equality. Eles já resolveram distribuição de educação offline em 220+ países. Não tem IA, mas a engenharia de distribuição e sincronização é referência mundial.

#### O que estudar

- **Kolibri Learning Platform** — github.com/learningequality/kolibri — A plataforma principal. Estude como eles fazem sincronização peer-to-peer via Wi-Fi local, compressão de conteúdo, e distribuição via sneakernet (literalmente carregar um dispositivo até a comunidade remota).

- **Kolibri Studio** — Ferramenta de curadoria de conteúdo curricular. Relevante para como o Seedlight organiza e distribui o Curriculum Graph.

- **Documentação de implementação** — learningequality.org — Eles documentam como implantaram em campos de refugiados, escolas rurais, contextos sem eletricidade. Isso é conhecimento operacional que não está em nenhum paper.

### 8.2 Estudo de Caso Arquitetural: Project N.O.M.A.D.

O Project N.O.M.A.D. (Node for Offline Media, Archives, and Data) é um servidor offline open-source que integra exatamente os building blocks que o Seedlight precisa — mas para um propósito diferente (sobrevivencialismo/off-grid). Estudá-lo é obrigatório porque ele já montou e testou a stack base.

#### Repositório

- **github.com/Crosstalk-Solutions/project-nomad** — 13k+ stars, Apache 2.0, em desenvolvimento ativo.

#### O que estudar

- **Orquestração de serviços com Docker** — como o N.O.M.A.D. gerencia Ollama, Qdrant, Kiwix, Kolibri e outros como containers Docker coordenados por um "Command Center". No Seedlight, os serviços seriam diferentes, mas o padrão de orquestração é reutilizável.

- **Integração Ollama + Qdrant para RAG** — como eles conectam o LLM local ao banco vetorial para busca semântica com upload de documentos. O Seedlight vai usar GraphRAG (mais sofisticado), mas a base de Ollama + busca local é a mesma.

- **Content management offline** — como eles gerenciam download, armazenamento e acesso a conteúdo offline (Wikipedia, Khan Academy via Kolibri, mapas). O Seedlight precisa resolver o mesmo problema para o Curriculum Graph e conteúdo educacional.

- **Setup wizard e configuração** — como eles guiam o usuário na primeira configuração e na seleção de conteúdo. Relevante para como o Seedlight seria configurado para uma criança/escola/comunidade específica.

- **Hardware guide** — eles documentam builds em três faixas de preço ($150-$1000+). Referência para o hardware guide do Seedlight.

#### Diferença Fundamental: N.O.M.A.D. vs. Seedlight

O N.O.M.A.D. é uma biblioteca offline com chatbot genérico (Vector RAG simples). O Seedlight é um sistema pedagógico inteligente com GraphRAG, múltiplos modelos de ML coordenados, memória longitudinal, e um LLM especializado em tutoria. A complexidade é de outra ordem — mas os building blocks de infraestrutura são validações reais de que a base funciona.

### 8.3 A Stack Completa de ML no Dispositivo

Esta seção descreve o ecossistema completo de modelos que rodariam dentro do dispositivo Seedlight, coordenados pelo orquestrador do Companion. Isso é o que faz o Seedlight ser fundamentalmente diferente de qualquer coisa que existe.

#### Componentes da Stack

**1. LLM Especializado (IA Generativa)** — Modelo de 1-3B parâmetros, treinado com RL para tutoria educacional (ver Área 5.3). É o que conversa com a criança. Roda via llama.cpp. Não opera sozinho — recebe contexto montado pelo orquestrador com informações de todos os outros componentes.

**2. Knowledge Tracing / BKT (IA Tradicional)** — Bayesian Knowledge Tracing rodando continuamente em background. Ultra-leve, consome recursos mínimos. Atualiza probabilidades de domínio de cada conceito para cada aprendiz a cada interação. Alimenta o grafo e informa o LLM sobre o que a criança sabe e não sabe.

**3. Detector de Estado de Engajamento (IA Tradicional)** — Modelo leve (pode ser baseado em regras ou ML clássico) que analisa padrões de interação: tempo de resposta, taxa de erros, abandono de sessão, padrões de retorno. Classifica se a criança está engajada, frustrada, entediada ou em flow. Modula o tom e a abordagem do LLM.

**4. Context Adapter (Híbrido)** — Módulo que transforma conceitos abstratos em exemplos do mundo da criança. Consulta o grafo para saber que contextos funcionam para aquela criança específica (rio, cozinha, futebol, etc.) e instrui o LLM a usar esses contextos nas explicações.

**5. Motor de GraphRAG Local** — Travessa o curriculum graph + learner profile para montar o contexto ideal para cada interação do LLM. Decide quais conceitos são relevantes, quais conexões explorar, e quais informações do perfil histórico incluir.

**6. Equity Signal Layer (Servidor/Nuvem — quando há conexão)** — Não roda no dispositivo. Quando há sincronização oportunista, analisa padrões agregados e anonimizados e envia recomendações de exposição a novos campos de conhecimento. O dispositivo funciona 100% sem isso.

#### Como os Componentes se Coordenam

O fluxo de uma interação típica seria: a criança faz uma pergunta ou completa uma atividade → BKT atualiza estado de domínio → Detector de engajamento avalia estado emocional → GraphRAG traversa o grafo para encontrar conceitos/contextos relevantes → Context Adapter seleciona o melhor veículo pedagógico → Orquestrador monta o prompt com todo esse contexto → LLM gera resposta personalizada → resposta é exibida → ciclo recomeça.

Isso tudo precisa acontecer em segundos, num dispositivo com recursos limitados. A engenharia de eficiência é o desafio central.

### 8.2 Software Offline-First

#### Paper Fundamental

- **"Local-First Software: You Own Your Data, in spite of the Cloud"** — Kleppmann et al. (2019). O paper que define software local-first. Os 7 princípios que ele apresenta são quase um checklist para o Seedlight: funciona offline, dados locais são a cópia principal, a rede é usada oportunisticamente.

#### Conceitos e Tecnologias

- **CRDTs (Conflict-free Replicated Data Types)** — Se dois dispositivos editam dados offline e depois sincronizam, CRDTs resolvem conflitos automaticamente. Relevante se a criança usa o dispositivo em casa e os dados eventualmente sincronizam com um hub escolar.

- **Automerge** — github.com/automerge/automerge — Implementação madura de CRDTs para dados JSON. Potencial base para sincronização do Learner Profile entre dispositivos.

### 8.3 Raspberry Pi como Plataforma de Desenvolvimento

#### O que comprar

- **Raspberry Pi 5 — 8GB** (~$80). O modelo de desenvolvimento obrigatório. Se funciona aqui, funciona em qualquer smartphone com specs equivalentes.
- **Case com cooler ativo** — Inferência de LLM é carga sustentada, vai fazer throttle térmico sem cooler.
- **MicroSD de 64GB classe A2** (ou melhor: SSD NVMe via HAT M.2, que reduz tempo de loading de modelos em ~70%).
- **Fonte de 27W USB-C oficial** — Fonte subdimensionada causa instabilidade sob carga.

#### Atividade Prática: Benchmark do Seedlight

1. Instale Raspberry Pi OS 64-bit ou Ubuntu Server
2. Instale Ollama
3. Baixe os modelos candidatos em Q4_K_M
4. Para cada modelo, meça: tokens/segundo em diálogo pedagógico, RAM consumida, tempo de cold start, temperatura sob carga
5. Teste com prompts educacionais em português: explicar frações, contar uma história sobre o ciclo da água, fazer perguntas socráticas sobre um texto
6. Documente tudo — este benchmark define qual modelo o Seedlight usa

### 8.4 Redes Mesh e Conectividade Comunitária

Não é responsabilidade do Seedlight construir redes, mas entender o ecossistema ajuda a projetar como dispositivos Seedlight se conectam quando há oportunidade.

#### Referências

- **Wakoma Nimble** — wakoma.co — Sistema open-source de rede mesh portátil e de baixo custo. Permite que comunidades construam conectividade local para educação, saúde e comércio. Referência para como Seedlight poderia se integrar em redes comunitárias existentes.

- **"Wireless Network in the Developing World"** — wndw.net — Guia prático gratuito sobre construção de redes wireless em comunidades.

---

## Área 9 — Padrões Abertos em Educação

**Por que isso importa:** O Seedlight se propõe a ser um protocolo aberto. Já existem padrões no campo educacional. Adotá-los onde fazem sentido dá credibilidade e interoperabilidade.

### 9.1 Padrões Existentes

- **xAPI (Experience API)** — Padrão para rastrear experiências de aprendizagem como "statements" (ator + verbo + objeto). Muito mais flexível que SCORM. O Learner Profile Engine deveria emitir dados neste formato.

- **LTI (Learning Tools Interoperability)** — Padrão para integrar ferramentas com plataformas educacionais. Relevante se o Seedlight se integrar com escolas.

- **IEEE Standard for Learning Technology — Data Model for Reusable Competency Definitions** — Para definição de competências no Curriculum Graph.

### 9.2 Protocolos de Integração de IA

- **Model Context Protocol (MCP)** — Protocolo da Anthropic para integração de LLMs com ferramentas externas. Relevante para como o Companion se conecta ao Curriculum Graph e ao Learner Profile Engine no dispositivo.

- **OpenAPI Specification** — Para documentação de APIs internas do sistema.

---

## Área 10 — Modelagem Preditiva de Tendências e Oportunidades

**Por que isso importa:** O Predictive Equity Layer precisa identificar campos emergentes e oportunidades futuras. Isso é análise de tendências tecnológicas e econômicas — e roda no servidor/nuvem, não no dispositivo da criança.

### 10.1 Análise de Tendências

- **"Quantifying the Evolution of Individual Scientific Impact"** — Sinatra et al. (2016). Modela como campos emergem e crescem.

- **"Predicting Future Scientific Discoveries Based on a Networked Analysis of the Past Literature"** — Rzhetsky et al. (2015). Usa grafos de conhecimento para prever descobertas.

### 10.2 Labor Market Intelligence

- **"The Growing Importance of Social Skills in the Labor Market"** — Deming (2017). Que habilidades estão crescendo.
- **O*NET** — onetonline.org — Base de dados de ocupações e habilidades.
- **World Economic Forum — Future of Jobs Reports** — Sinais sobre habilidades futuras.

---

## Área 11 — Design e Experiência do Usuário para Crianças

**Por que isso importa:** O usuário final é uma criança, possivelmente segurando um dispositivo pela primeira vez. A interface precisa ser intuitiva para quem talvez nunca usou um tablet. Designing for children is fundamentally different.

### 11.1 Design para Crianças

- **"Interaction Design and Children"** — Conferência IDC. Proceedings recentes. Principal venue acadêmico sobre design para crianças.

- **"Design Principles for Children's Technology"** — Druin (2009). Crianças como parceiras no design, não apenas usuárias.

- **"Children's Rights by Design"** — UNICEF (2020). Framework para tecnologia que respeita direitos das crianças.

### 11.2 Interfaces para Contextos de Baixa Literacia Digital

- Interfaces baseadas em voz (text-to-speech e speech-to-text) podem ser mais acessíveis que texto para crianças em início de alfabetização
- Ícones e navegação visual em vez de menus textuais
- Modos de alto contraste e baixo consumo de bateria

### 11.3 Visualização do Mapa Cognitivo

- **"Learning Analytics Dashboards"** — Schwendimann et al. (2017). Survey de dashboards de learning analytics.

---

## Área 12 — Engenharia de Software e Arquitetura de Sistemas

**Por que isso importa:** Tudo acima é teoria e pesquisa. Isso aqui transforma ideias em sistema.

### 12.1 Arquitetura do Dispositivo Seedlight

O stack técnico no dispositivo seria:
- **llama.cpp** como runtime de inferência do LLM
- **SQLite** como banco de dados local (perfil do aprendiz, curriculum graph, histórico de interações)
- **SQLite VSS** para busca vetorial local (RAG)
- **BKT/modelo de knowledge tracing** rodando como processo leve em paralelo
- **App nativo ou PWA leve** como interface da criança
- **Servidor HTTP local** (llama.cpp server) para comunicação entre app e modelo

### 12.2 Referências de Arquitetura

- **"Designing Data-Intensive Applications"** — Martin Kleppmann (2017). O livro de referência sobre arquitetura de dados.

- **OpenCode** — github.com/sst/opencode — Estudar como referência de: arquitetura cliente/servidor, gerenciamento de sessões com SQLite, auto-compactação de contexto, agnosticismo de provedor de LLM. Ver Área 4.4 para detalhes.

- **Project N.O.M.A.D.** — github.com/Crosstalk-Solutions/project-nomad — Estudar como referência de: orquestração de serviços offline com Docker, integração Ollama + banco vetorial, gerenciamento de conteúdo offline, setup wizard. Ver Área 8.2 para detalhes.

### 12.3 Infraestrutura de ML

- **MLflow** — github.com/mlflow/mlflow — Gerenciamento do ciclo de vida de ML. Para rastrear experimentos com modelos de knowledge tracing e fine-tuning.

- **DVC** — github.com/iterative/dvc — Versionamento de dados e modelos.

---

## Ordem de Estudo Recomendada

A ordem não é arbitrária. Cada fase constrói sobre a anterior.

### Fase 1 — Fundação Conceitual (Semanas 1-4)

Comece pela **Área 1** (Ciências da Aprendizagem). Leia Mindstorms de Papert e How People Learn. Sem isso, todo o resto é engenharia sem propósito. Em paralelo, leia a **Área 6.1** (Fairness em ML) — especialmente Selbst et al. e fairmlbook.org.

### Fase 2 — Hardware e Modelos Pequenos (Semanas 5-8)

**Compre o Raspberry Pi 5.** Instale Ollama, teste os modelos candidatos, faça o benchmark descrito na Área 8.3. Em paralelo, estude a **Área 5** (Quantização e Modelos Pequenos) e a **Área 2.2** (Knowledge Tracing). Implemente pyBKT. Esta fase é onde o abstrato vira concreto.

### Fase 3 — Agentes, GraphRAG e Referências Arquiteturais (Semanas 9-12)

Estude a **Área 4** (Agentes com Primitivas). Leia todos os blogs da Anthropic. Estude o código-fonte do **OpenCode** (github.com/sst/opencode) — foque na arquitetura cliente/servidor, sessões SQLite, e auto-compact. Estude a **Área 3.3** (GraphRAG) — leia o survey do arXiv e o paper da Microsoft. Explore o **nano-graphrag** como implementação leve. Comece a prototipar o Companion: um agente simples rodando no Pi com memória persistente em SQLite e um curriculum graph básico.

### Fase 4 — Infra Offline e Estudos de Caso (Semanas 13-16)

Estude o **Project N.O.M.A.D.** (github.com/Crosstalk-Solutions/project-nomad) — instale no Pi, explore a integração Ollama+Qdrant, entenda a orquestração Docker. Estude o **Kolibri** (Área 8.1). Aprofunde na **Área 6** (Equidade), **Área 7** (Privacidade) e **Área 9** (Padrões). Estude Federated Learning com Flower. Leia legislação (LGPD, GDPR).

### Fase 5 — Treinamento Especializado e Integração (Semanas 17-20)

**Área 5.3** (Treinamento com RL) — estude o DeepResearcher e o veRL. Comece a planejar como treinar um modelo especializado para tutoria. **Áreas 10, 11 e 12** — Modelagem preditiva, design para crianças, e arquitetura final.

### Fase 6 — Protótipo Completo (Semanas 21-24)

Integrar tudo: um protótipo funcional rodando no Raspberry Pi com a stack completa descrita na Área 8.3 — LLM especializado, BKT, detector de engajamento, GraphRAG local, Context Adapter, memória persistente, e interface mínima. Testar com uma criança real (com consentimento e supervisão dos pais). Documentar tudo para o primeiro release público.

---

## Nota Final

Este guia é extenso porque o problema é extenso. A decisão de colocar o LLM no dispositivo é ambiciosa — e é a decisão certa. Ela força o projeto a ser engenhoso em vez de dependente, e garante que a solução funcione exatamente onde é mais necessária.

Cada área listada aqui existe porque sem ela, algum componente do Seedlight será frágil, ingênuo, ou perigoso. Você não precisa virar especialista em tudo. Precisa ter compreensão suficiente para tomar decisões de design informadas e para saber quando precisa de ajuda.

A boa notícia: você tem um Pi, um mentor, e uma convicção. Isso é suficiente para começar.

Vamos construir isso com seriedade. 🌱
