🧠 Classificação de Tumores Cerebrais com Deep Learning
Este repositório contém a implementação e análise comparativa dos modelos EfficientNet-B0, Swin Transformer e ConvNeXt na classificação de tumores cerebrais em imagens de ressonância magnética.

📌 Resumo

Objetivo: Classificar tumores cerebrais usando modelos de deep learning.
Modelos Testados: EfficientNet-B0, Swin Transformer e ConvNeXt.
Técnicas Aplicadas: Transfer Learning, Fine-Tuning e Data Augmentation.
Dataset: Imagens de ressonância magnética de tumores cerebrais.
Divisão: 80% treino/validação, 20% teste.
Métricas Avaliadas: Precisão, F1-score, Recall e Curva ROC.

🚀 Resultados

Modelo	Acurácia
Swin Transformer	97%
ConvNeXt	94%
EfficientNet-B0	93%

📂 Dataset
O dataset utilizado neste projeto pode ser acessado no Kaggle:

🔗[Dataset de origem (Figshare)](https://figshare.com/articles/dataset/brain_tumor_dataset/1512427)

🔗[Link para o dataset no Kaggle](https://www.kaggle.com/code/reidnersantos/convnext-figshare-braintumor/input)


📜 Metodologia

Pré-processamento: Redimensionamento, normalização e Data Augmentation.
Treinamento: Transfer learning e fine-tuning nos três modelos.
Avaliação: Teste dos modelos com métricas de desempenho.

🛠️ Tecnologias Utilizadas

Python
TensorFlow / Keras
NumPy, Pandas, Matplotlib

📌 Repositório no Kaggle

Modelos sem Data Augmentation

🔗[Efficient](https://www.kaggle.com/code/reidnersantos/efficientnet-figshare-braintumor)

🔗[Swin Transformer](https://www.kaggle.com/code/reidnersantos/swin-transformer-figshare-braintumor-fork)

🔗[ConvNeXt](https://www.kaggle.com/code/reidnersantos/convnext-figshare-braintumor)

Modelos com Data Augmentation

🔗[Efficienet](https://www.kaggle.com/code/jackssonyuri/efficientnet-figshare-braintumor-with-aug)

🔗[Swin Transformer](https://www.kaggle.com/code/jackssonyuri/swin-transformer-figshare-braintumor-with-aug-1)

🔗[ConvNeXt](https://www.kaggle.com/code/jackssonyuri/convnext-figshare-braintumor-with-aug)


