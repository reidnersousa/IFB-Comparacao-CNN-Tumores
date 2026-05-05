# 🧠 Classificação de Tumores Cerebrais Utilizando Redes Neurais Convolucionais

Trabalho de Conclusão de Curso (TCC)
Bacharelado em Ciência da Computação
Instituto Federal de Brasília (IFB) - Campus Taguatinga | 2024

## 📋 Resumo Executivo
Este projeto implementa e compara múltiplas arquiteturas de deep learning para classificação automática de tumores cerebrais em imagens de ressonância magnética (RM). O trabalho avalia o desempenho de CNNs clássicas (EfficientNet-B0, ConvNeXt) e Vision Transformers (Swin Transformer) em um dataset de 3.060+ imagens médicas.
## 🎯 Objetivos

- **Objetivo Geral:** Avaliar se a arquitetura puramente convolucional (EfficientNet-B0) mantém sua eficiência na classificação de tumores cerebrais quando comparada a arquiteturas mais recentes (ConvNeXt) e baseadas em Transformers (Swin Transformer).
- **Objetivos Específicos:**
    - Implementar técnicas de **Transfer Learning** e **Fine-Tuning** para ajuste de pesos nos três modelos avaliados.
    - Analisar o impacto do **Data Augmentation** na estabilidade do treinamento e nas métricas de generalização.
    - Otimizar o pipeline de processamento de dados para contornar limitações de memória e hardware.
    - Avaliar os resultados utilizando métricas padrão de classificação: F1-score, Curva ROC (AUC), Precisão e Recall.

## 👥 Autores e Orientação

- **Autores:** Jacksson Yuri de Amorim Wasterloô e Reidner Sousa dos Santos
- **Orientador:** Prof. Fabiano Cavalcanti Fernandes
- **Instituição:** Instituto Federal de Brasília (IFB)

## 🛠️ Tecnologias e Ferramentas

- **Linguagem:** Python
- **Ambiente de Desenvolvimento:** Kaggle Notebooks
- **Frameworks & Bibliotecas:** TensorFlow, Keras, OpenCV (cv2), NumPy, tfswin
- **Modelos Avaliados:** EfficientNet-B0, ConvNeXt, Swin Transformer

## ⚙️ Ambiente de Treinamento e Desafios Computacionais

Todos os experimentos foram realizados sob as mesmas condições de hardware no Kaggle, utilizando um acelerador **GPU NVIDIA Tesla P100**. A configuração de treinamento seguiu um padrão de 30 épocas na fase de Transfer Learning + 30 épocas no Fine-Tuning.

Durante o desenvolvimento, algumas limitações de memória do ambiente Kaggle exigiram fortes otimizações no código de pré-processamento:

- **Resolução das Imagens:** As imagens originais de 512x512 pixels foram redimensionadas para 256x256 pixels utilizando o OpenCV.
- **Otimização de Memória (Crucial):** O uso de listas nativas do Python (método `append()`) causava estouro de memória (Out of Memory - OOM). **A solução foi a adoção de arrays do NumPy com alocação prévia de memória**, o que reduziu drasticamente o tempo de processamento e garantiu a estabilidade do pipeline.
- **Instalação do Swin Transformer:** Para evitar conflitos de dependência com a versão do TensorFlow nativa do Kaggle, o pacote precisou ser instalado isoladamente utilizando o comando: `pip install tfswin --no-deps`.

## 📊 Conjunto de Dados (Dataset)

O conjunto de dados utilizado no projeto foi dividido na seguinte proporção:

- **Treinamento:** 80%
- **Validação:** 10%
- **Teste:** 10%


🔗[Dataset de origem (Figshare)](https://figshare.com/articles/dataset/brain_tumor_dataset/1512427)  
🔗[Link para o dataset no Kaggle](https://www.kaggle.com/code/reidnersantos/convnext-figshare-braintumor/input) 

## 📓 Como Executar (Notebooks no Kaggle)

Todo o código-fonte, treinamento e validação dos modelos foram desenvolvidos e estão disponíveis publicamente no Kaggle.

Para reproduzir os resultados, certifique-se de ativar o acelerador **GPU P100** e instalar o `tfswin` conforme mencionado acima. Os experimentos foram divididos em abordagens com e sem aumento de dados:

### Modelos SEM Data Augmentation

| Modelo | Link de Acesso |
| --- | --- |
| **EfficientNet** | [Efficient](https://www.kaggle.com/code/reidnersantos/efficientnet-figshare-braintumor) |
| **Swin Transformer** | [Swin Transformer](https://www.kaggle.com/code/reidnersantos/swin-transformer-figshare-braintumor-fork) |
| **ConvNeXt** | [ConvNeXt](https://www.kaggle.com/code/reidnersantos/convnext-figshare-braintumor) |

### Modelos COM Data Augmentation

| Modelo | Link de Acesso |
| --- | --- |
| **EfficientNet** | [Efficienet](https://www.kaggle.com/code/jackssonyuri/efficientnet-figshare-braintumor-with-aug) |
| **Swin Transformer** | [Swin Transformer](https://www.kaggle.com/code/jackssonyuri/swin-transformer-figshare-braintumor-with-aug-1) |
| **ConvNeXt** | [ConvNeXt](https://www.kaggle.com/code/jackssonyuri/convnext-figshare-braintumor-with-aug) |

## 📈 Resultados e Conclusões

A análise comparativa demonstrou que redes neurais baseadas em Transformers são extremamente poderosas na visão computacional médica. O modelo **Swin Transformer foi o grande destaque**, provando ser o mais eficaz para a classificação dos três tipos de tumores cerebrais neste dataset.

| Modelo | Acurácia | Destaque e Comportamento |Custo Computacional |
| --- | --- | --- | --- | 
| 🏆 **Swin Transformer** | **0.97** | **Melhor desempenho geral. Beirou a perfeição nas métricas, apresentando a menor taxa de erro na matriz de  confusão, inclusive para a classe mais desafiadora (glioma). Data Augmentation trouxe maior estabilidade às curvas de perda.** | **Alto** |
| 🥈 **ConvNeXt** | 0.94 | Sem Data Augmentation, apresentou dificuldade com a classe meningioma. A aplicação do aumento de dados foi crucial, reduzindo a confusão entre classes e subindo o AUC do meningioma em +0.01. | Médio |
| 🥉 **EfficientNet-B0** | 0.93 | Resultados sólidos, mas com maior dificuldade em encontrar o equilíbrio ideal entre precisão e recall. Data Augmentation foi essencial para mitigar a confusão entre meningioma e glioma. | Baixo | 



---

## 📄 Licença

**MIT License**

Copyright (c) 2026 Jacksson Yuri de Amorim Wasterloô, Reidner Sousa dos Santos

*Trabalho desenvolvido no Instituto Federal de Brasília (IFB) - Campus Taguatinga.*

Permissão é concedida, gratuitamente, a qualquer pessoa que obtenha uma cópia deste software e dos arquivos de documentação associados (o "Software"), para lidar com o Software sem restrições, incluindo, sem limitação, os direitos de usar, copiar, modificar, mesclar, publicar, distribuir, sublicenciar e/ou vender cópias do Software, sujeito às seguintes condições:

O aviso de direitos autorais acima e este aviso de permissão devem ser incluídos em todas as cópias ou partes substanciais do Software.
