---
kind: lesson
sources: []
seedlight-component: companion
tags: #foundational
---

# SFT vs RL como Analogia Educacional

O pipeline de treinamento de LLMs espelha o que a pesquisa educacional mostra sobre aprendizagem humana — uma ironia produtiva que valida ambos os campos.

## A analogia

**SFT (Supervised Fine-Tuning)** e instrucao direta — o modelo ve exemplos corretos e imita. E o [[two-sigma-problem]] de Bloom aplicado a maquina: "quando a crianca pergunta X, o tutor responde Y". O modelo aprende o formato, o tom, a estrutura. Limitacao: so aprende o que o "professor" mostrou.

**RL (Reinforcement Learning)** e [[productive-failure]] de Kapur — o modelo gera respostas livremente, erra, recebe feedback (reward signal), e descobre caminhos que nenhum exemplo demonstrou. O DeepSeek-R1 mostrou que GRPO ensinou modelos a raciocinar de formas que nao existiam nos dados de treinamento — o modelo "inventou" estrategias de raciocinio.

O pipeline **base → SFT → RL** faz as duas coisas em sequencia: SFT da o chao (formato, tom, estrutura), RL descobre o como (estrategias emergentes de tutoria).

## Por que importa para o Seedlight

A analogia nao e so elegante — e funcional. As [[desirable-difficulties]] de Bjork mostram que luta produtiva gera retencao superior. Se isso e verdade pra humanos, o RL sugere que e verdade tambem pra modelos: o treinamento por tentativa-e-erro (RL) produz capacidades que o treinamento por imitacao (SFT) nao consegue. O Companion sera treinado do mesmo jeito que a pesquisa diz que criancas aprendem melhor.
