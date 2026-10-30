# 🏥 Domando Gigantes: Transformando LLMs de Código Aberto em Especialistas

Bem-vindo ao repositório oficial da palestra do **DevFest 2026** ministrada por **Fernanda Wanderley**. 

Este repositório contém o código completo para realizar o fine-tuning (ajuste fino) do **Gemma 2B** (Google) utilizando **Keras 3** e **JAX**, transformando um modelo generalista em um assistente médico especialista, rodando de forma 100% gratuita na nuvem (Kaggle/Colab).

## 🚀 O que você vai aprender com este código?

*   **Keras 3 Backend Agnóstico:** Como escrever um código que roda em JAX, TensorFlow ou PyTorch mudando apenas uma linha.
*   **Engenharia Anti-OOM (Out of Memory):** Como impedir que o compilador XLA sequestre toda a memória da sua GPU T4 usando alocação dinâmica e precisão `bfloat16`.
*   **LoRA (Low-Rank Adaptation):** Como treinar um LLM de 2 bilhões de parâmetros congelando o "cérebro" original e gastando processamento apenas em matrizes de adaptação minúsculas (Rank=8).
*   **Matemática de Sobrevivência:** O uso de `clipnorm` no otimizador para evitar saltos matemáticos explosivos em *batch sizes* pequenos.

## 🛠️ Stack Tecnológico
*   [Kaggle Notebooks](https://www.kaggle.com/) (Infraestrutura / 1x GPU T4 15GB)
*   [Keras 3](https://keras.io/keras_3/) (Framework MLOps)
*   [Gemma 2B](https://ai.google.dev/gemma) (Modelo Fundacional)
*   [Hugging Face Datasets](https://huggingface.co/docs/datasets/) (Pipeline de Dados)

## 📦 Como rodar este projeto?

1. Crie um notebook no Kaggle e ative a **GPU T4 x2** (embora usemos apenas 1 no código para evitar gargalos de rede NCCL).
2. Adicione as suas chaves nas configurações do Kaggle (`Add-ons > Secrets`):
    * `KAGGLE_USERNAME` e `KAGGLE_KEY` (Para baixar o Gemma)
    * `HF_TOKEN` (Para baixar o dataset Medical Meadows sem restrições de rede)
3. Copie o código do arquivo `gemma_medico_finetuning.py` para as células do seu notebook.
4. Execute e acompanhe a mágica acontecer!

## 📊 O Paradoxo do Treinamento (Resultados)
Na nossa palestra, mostramos que o fine-tuning de LLMs exige cautela. 
*   **Zero-Shot (Base):** Sofre de "translation bleed" (traduz para o inglês sozinho) e corta as respostas.
*   **Época 3:** Responde estruturadamente em português com precisão cirúrgica.
*   **Época 10 (Overfitting):** Sofre lavagem cerebral, decora o dataset e desaprende o idioma.

## 🤝 Conecte-se
*   **LinkedIn:** [Fernanda Wanderley](http://linkedin.com/in/nandaw)
 

---
*Desenvolvido para fins educacionais e de demonstração arquitetural. Não utilize modelos de linguagem abertos em produção médica sem validação (LLM-as-a-Judge) e auditoria humana rigorosa.*
