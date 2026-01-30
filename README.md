# Classificação de Imagens com Transfer Learning

### Cães vs. Gatos usando CNN e VGG16

![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN-green)
![Status](https://img.shields.io/badge/Status-Concluído-success)

---

## 📌 Sobre o Projeto

Este projeto explora, de forma prática, o uso de **Transfer Learning** para classificação de imagens, comparando o desempenho de dois modelos:

* Uma **Rede Neural Convolucional (CNN)** treinada do zero
* Um modelo baseado na **VGG16**, pré-treinada no dataset ImageNet

O objetivo é evidenciar os ganhos em desempenho, velocidade de treinamento e generalização ao utilizar modelos pré-treinados.

---

## 🎯 Objetivo

Avaliar o impacto do Transfer Learning na tarefa de classificação de imagens entre cães e gatos, considerando:

* Acurácia
* Estabilidade do treinamento
* Capacidade de generalização

Especialmente em cenários com volume limitado de dados.

---

## 🛠️ Tecnologias Utilizadas

* **Python**
* **TensorFlow / Keras**
* **NumPy**
* **Matplotlib**
* **Google Colab**

---

## 🧠 Metodologia

### 1. Pré-processamento dos Dados

* Dataset: *Kaggle Cats and Dogs*
* Redimensionamento das imagens para **224x224**
* Normalização dos pixels (0–1)
* One-hot encoding das classes
* Divisão dos dados:

  * Treino: 70%
  * Validação: 15%
  * Teste: 15%
* Limite de **500 imagens por classe** para otimização de recursos

---

### 2. CNN Treinada do Zero

* Arquitetura sequencial com:

  * Camadas convolucionais
  * MaxPooling
  * Dropout
  * Camadas densas
* Função de perda: `categorical_crossentropy`
* Otimizador: `Adam`
* Treinamento por **10 épocas**

---

### 3. Transfer Learning com VGG16

* Uso da arquitetura **VGG16** pré-treinada na ImageNet
* Camadas convolucionais congeladas
* Substituição da camada final por um classificador `Dense + Softmax`
* Treinamento apenas da nova camada de saída
* Treinamento por **10 épocas**

---

## 📊 Resultados

| Modelo                    | Acurácia de Teste | Loss  |
| ------------------------- | ----------------- | ----- |
| CNN do Zero               | 63.33%            | 0.661 |
| VGG16 (Transfer Learning) | 88.67%            | 0.326 |

### 🔎 Observações

* O modelo com Transfer Learning apresentou aprendizado mais rápido e estável
* Melhor desempenho mesmo com menos dados
* A CNN treinada do zero apresentou maior dificuldade de convergência

---

## 🚀 Como Executar

1. Abra o notebook no **Google Colab**
2. Execute todas as células em sequência
3. Para testar com imagens próprias:

   * Substitua `dog_test.jpg` ou `cat_test.jpg`
   * Execute a célula de predição

---

## ✅ Conclusão

O uso de Transfer Learning mostrou-se altamente eficiente para problemas de visão computacional, entregando melhores resultados com menor custo computacional. A VGG16 demonstrou excelente capacidade de generalização, mesmo com um conjunto de dados reduzido.

---

## 📎 Referências

* Dataset: Kaggle Cats and Dogs
* Modelo: VGG16 (ImageNet)
* Documentação TensorFlow / Keras
