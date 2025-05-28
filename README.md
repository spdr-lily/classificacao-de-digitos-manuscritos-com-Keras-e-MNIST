# **Projeto de Classificação de Dígitos Manuscritos com Keras e MNIST**

## **1\. Introdução**

Este projeto demonstra o desenvolvimento de um modelo de rede neural para classificar dígitos manuscritos utilizando a biblioteca Keras e o conjunto de dados MNIST. O objetivo é construir um modelo capaz de reconhecer e classificar corretamente dígitos de 0 a 9 a partir de imagens.

## **2\. Metodologia**

### **2.1. Conjunto de Dados**

O conjunto de dados MNIST foi utilizado para treinar e testar o modelo. Ele consiste em 60.000 imagens de treinamento e 10.000 imagens de teste, cada uma sendo uma imagem em escala de cinza de 28x28 pixels representando um dígito manuscrito.

### **2.2. Bibliotecas Utilizadas**

* **NumPy:** Para manipulação eficiente de arrays e operações numéricas.  
* **Keras:** Uma biblioteca de alto nível para construir e treinar redes neurais.  
* **TensorFlow:** Backend para Keras, utilizado para computação numérica.

### **2.3. Pré-processamento dos Dados**

1. **Carregamento dos Dados:** O conjunto de dados MNIST foi carregado utilizando a função `mnist.load_data()` do Keras, que retorna os conjuntos de treinamento e teste.  
2. **Normalização:** As imagens foram normalizadas dividindo os valores dos pixels por 255.0 para garantir que todos os valores estejam na faixa de 0 a 1\. Isso ajuda a acelerar o treinamento e melhorar a estabilidade do modelo.  
3. **Codificação One-Hot:** Os rótulos (labels) dos dígitos foram convertidos para a representação one-hot utilizando a função `to_categorical()` do Keras. Isso é necessário para a função de perda `categorical_crossentropy`.

### **2.4. Arquitetura do Modelo**

O modelo de rede neural foi construído utilizando a API Sequential do Keras e consiste nas seguintes camadas:

1. **Flatten:** Transforma a imagem de entrada de 28x28 pixels em um vetor de 784 elementos.  
2. **Dense (128 unidades, ReLU):** Uma camada densamente conectada com 128 neurônios e função de ativação ReLU.  
3. **Dense (64 unidades, ReLU):** Outra camada densamente conectada com 64 neurônios e função de ativação ReLU.  
4. **Dense (10 unidades, Softmax):** A camada de saída com 10 neurônios (um para cada classe de dígito) e função de ativação Softmax, que produz probabilidades para cada classe.

### **2.5. Compilação e Treinamento do Modelo**

* **Otimizador:** O otimizador 'adam' foi utilizado para treinar o modelo.  
* **Função de Perda:** A função de perda `categorical_crossentropy` foi utilizada, adequada para problemas de classificação multiclasse.  
* **Métricas:** A métrica 'accuracy' foi utilizada para avaliar o desempenho do modelo durante o treinamento.

O modelo foi treinado por 5 épocas com um tamanho de lote (batch size) de 32 e uma divisão de validação de 10%.

### **2.6. Avaliação do Modelo**

Após o treinamento, o modelo foi avaliado utilizando o conjunto de teste. A perda (loss) e a acurácia foram calculadas para medir o desempenho do modelo em dados não vistos.

## **3\. Resultados**

Os resultados da avaliação do modelo no conjunto de teste são os seguintes:

* **Perda (Loss):** 0.2604  
* **Acurácia (Accuracy):** 0.9238

Isso indica que o modelo foi capaz de classificar os dígitos manuscritos com uma acurácia de aproximadamente 92.38% no conjunto de teste.

## **4\. Discussão**

O modelo alcançou uma alta acurácia na classificação dos dígitos MNIST, demonstrando a eficácia das redes neurais para esta tarefa. A normalização dos dados e a escolha adequada da arquitetura do modelo e dos hiperparâmetros foram cruciais para o desempenho do modelo.

## **5\. Conclusão**

Este projeto demonstrou a implementação bem-sucedida de um modelo de rede neural para a classificação de dígitos manuscritos utilizando Keras e o conjunto de dados MNIST. O modelo alcançou uma alta acurácia, validando a eficácia das redes neurais para tarefas de reconhecimento de imagem.
