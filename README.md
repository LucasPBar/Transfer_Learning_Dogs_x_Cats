# Classificação de Imagens com Transfer Learning  
### Cães vs. Gatos com CNN e VGG16

![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN-green)
![Status](https://img.shields.io/badge/Status-Concluído-success)

---

## 📌 Visão Geral
Este projeto demonstra, na prática, o impacto do **Transfer Learning** na classificação de imagens. Utilizamos o dataset **Cats and Dogs** para comparar dois modelos de Deep Learning:  
- Uma **CNN treinada do zero**  
- Um modelo baseado na **VGG16 pré-treinada na ImageNet**

O foco é avaliar ganhos de desempenho, velocidade de treinamento e capacidade de generalização.

---

## 🎯 Objetivo
Avaliar como o uso de **Transfer Learning** influencia:
- Acurácia do modelo  
- Estabilidade do treinamento  
- Capacidade de generalização  
em comparação com uma CNN desenvolvida do zero, especialmente em cenários com dados limitados.

---

## 🛠️ Tecnologias Utilizadas
- **Python**
- **TensorFlow / Keras**
- **NumPy**
- **Matplotlib**
- **Google Colab**

---

## 🧠 Metodologia

### 1️⃣ Coleta e Pré-processamento
- Dataset: *Kaggle Cats and Dogs*
- Redimensionamento das imagens para **224x224**
- Normalização dos pixels (0–1)
- One-hot encoding das classes
- Divisão dos dados:
  - Treino: 70%
  - Validação: 15%
  - Teste: 15%
- Limite de **500 imagens por classe** para otimização de recursos

---

### 2️⃣ Modelo CNN do Zero
- Arquitetura sequencial com:
  - Camadas convolucionais
  - MaxPooling
  - Dropout
  - Camadas densas
- Função de perda: `categorical_crossentropy`
- Otimizador: `Adam`
- Treinamento por **10 épocas**

---

### 3️⃣ Modelo com Transfer Learning (VGG16)
- Uso da **VGG16 pré-treinada na ImageNet**
- Camadas convolucionais congeladas
- Nova camada de classificação com `softmax`
- Treinamento apenas do classificador final
- Treinamento por **10 épocas**

---

### 4️⃣ Avaliação e Comparação
- Comparação de:
  - Acurácia
  - Perda
  - Curvas de aprendizado
- Avaliação final com o conjunto de teste

---

## 📊 Resultados

| Modelo | Acurácia de Teste | Loss |
|------|------------------|------|
| CNN do Zero | **63.33%** | 0.661 |
| VGG16 (Transfer Learning) | **88.67%** | 0.326 |

### 🔎 Principais Insights
- O modelo com Transfer Learning apresentou:
  - Aprendizado mais rápido
  - Maior estabilidade
  - Melhor generalização
- A CNN treinada do zero demonstrou maior dificuldade em convergir e menor desempenho final.

---

## 🚀 Como Executar
1. Abra o notebook no **Google Colab**
2. Execute todas as células em sequência
3. Para testes personalizados:
   - Substitua `dog_test.jpg` ou `cat_test.jpg`
   - Execute a célula de predição

---

## ✅ Conclusão
O Transfer Learning mostrou-se uma abordagem altamente eficiente para tarefas de visão computacional, entregando melhores resultados com menos dados e menor custo computacional. O uso da VGG16 reforça como modelos pré-treinados aceleram o desenvolvimento e elevam a performance final.
