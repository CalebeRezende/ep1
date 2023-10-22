# Esse ep foi desenvolvido para disciplina de MAC5725 - Linguística Computacional

Calebe Macena Rezende, Nª USP: 9366151

É necessário realizar às seguintes importações: 

    
# Pré requisito
Meu carregamento só se deu usando o Google Colab Pro, usando a V100. Por isso, deixo como pré requisito.

# DATASET

Carregar o dataset da seguinte maneira:  https://raw.githubusercontent.com/americanas-tech/b2w-reviews01/main/B2W-Reviews01.csv --output 'B2W-Reviews01.csv' 

# Importações 
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
import seaborn as sns
from keras.preprocessing.sequence import pad_sequences
from sklearn.model_selection import train_test_split
from keras.models import Sequential
from keras.layers import Embedding, LSTM, Dense, Dropout, Bidirectional
from keras.preprocessing.text import Tokenizer
import pandas as pd
import tensorflow as tf
from keras.callbacks import ModelCheckpoint, EarlyStopping
from tensorflow.keras.utils import to_categorical
from tensorflow.keras.utils import plot_model
from keras.preprocessing.text import Tokenizer
from tensorflow.keras.models import load_model
from sklearn.metrics import confusion_matrix, classification_report

# Executar tudo
Como apresentado anteriormente, coloquei como pré requisito o Google Colab Pro, pois só dessa maneira, pude colocar um: Executar tudo. 

# Informações Adicionais
Há um jupyternotebook anexo nesse git, para que não se gaste recursos para o rodar, a análise desse notebook foi inserido em: Artigo NLP V10
Tais como gráficos, imagens e conclusões após rodar.

Não obtive um bom desempenho com acurácia, por conta de mau gerenciamento de tempo, mas há formas de se fazer isso, mesmo que para melhorias mínimas. 

Do córpus já mencionado, colunas relevantes foram extraídas da seguinte forma: 
B2WReviews01 = df[['review_text', 'overall_rating']]

Informações não relevantes, mas que fazem parte do relatório.

Os dados foram separados em 3 partes idealmente:
• Treinamento: 65%
• Validação: 10%
• Teste: 25%

Porém a quantidade exata da separação ficou: 
Tamanho do conjunto de treinamento: 80747
Tamanho do conjunto de validação: 19856
Tamanho do conjunto de teste: 31770

Foram importadas:
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
import seaborn as sns

O primeiro hiperparâmetro aqui trabalhado, foi:
Tamanho máximo de sequência: 795
Tamanho do vocabulário: 39855

O segundo hiperparâmetro foi:
Quantidade de pslavras conhecidas: 20000

Para completar, o batchsize foi de: 
32

A quantidade de épocas necessárias foi de: 52
Na 52: ocorreu o early stopping

Vamos aos dados de treinamento e teste: 
Para rodar os 3 ciclos de época, gastaram-se: 14 horas rodando, em V100, do google colab.

![image](https://github.com/CalebeRezende/ep1/assets/120114655/35260673-9cca-48d9-b692-4f74aadb52de)
![image](https://github.com/CalebeRezende/ep1/assets/120114655/cd446296-6be3-4537-b8a6-4a8e70728afb)
![image](https://github.com/CalebeRezende/ep1/assets/120114655/d8c1d414-814f-4a71-ab85-d40a4450f2e1)

![image](https://github.com/CalebeRezende/ep1/assets/120114655/575f9328-f67f-45b7-a666-4828f0e7fd07)
![image](https://github.com/CalebeRezende/ep1/assets/120114655/2dd9ed17-407c-49f6-b9ae-8da7e045b264)
![image](https://github.com/CalebeRezende/ep1/assets/120114655/2a734ae4-c1a9-42dd-8476-256890e9005e)

Para entender agora qual foi a acurácia no conjunto de teste: ![image](https://github.com/CalebeRezende/ep1/assets/120114655/ff5be29a-77a8-4dbf-b4ba-6f42809c2369)

Para computar essa perca: ![image](https://github.com/CalebeRezende/ep1/assets/120114655/2eead072-ab6d-4482-a086-0b0f5acaa7a7)

Matriz de confusão: 
![image](https://github.com/CalebeRezende/ep1/assets/120114655/8562acd1-2286-49cf-9ee4-a1de1327c2fd)
![image](https://github.com/CalebeRezende/ep1/assets/120114655/61230f17-f313-4155-b8d6-b380a8d549b1)




