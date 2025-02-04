# Desafio Técnico Minds Digital

Este repositório contém o código desenvolvido como parte do desafio técnico para a empresa Minds Digital, visando à posição de Cientista de Dados / Machine Learning Engineer (MLE).

## Objetivo

O objetivo deste desafio é utilizar modelos de Redes Neurais Convolucionais (CNNs) para a classificação de comandos de fala. Para isso, foram utilizados dois datasets diferentes.

## Datasets

### Atividade 1: Dataset Speech Commands v0.02

#### Preparação dos dados

- **Download e preparação**: o dataset foi baixado do link fornecido e extraído para o diretório `dataset`. Foi realizada a remoção de ruídos de fundo.
- **Divisão dos Dados**: o dataset foi dividido em listas de treino, validação e teste sem intersecção.

#### Criação do dataset customizado

- **Classe `CustomAudioDataset`**: implementada para carregar e processar os arquivos de áudio. A função `__getitem__` abre os arquivos de áudio e realiza o processamento necessário, incluindo padding e cálculo do espectrograma Mel.
- **Classes Balanceadas**: análise da distribuição das classes no conjunto de treino para verificar possíveis desbalanceamentos.

#### Modelo

- **Definição do modelo**: o modelo escolhido foi uma CNN com três camadas convolucionais seguidas de pooling e uma camada totalmente conectada com Dropout.

#### Treinamento

- **Configuração do treinamento**: utilizado o otimizador Adam e a função de perda CrossEntropyLoss. Adicionado um scheduler para ajustar a taxa de aprendizado.

#### Avaliação

- **Métricas**: foram calculadas métricas como acurácia, precisão, recall e F1-score utilizando a função `calculate_metrics`.

#### Resultados

- **Desempenho**: o modelo apresentou um bom desempenho na classificação de comandos de fala com acurácia e outras métricas de avaliação satisfatórias.

### Atividade 2: Custom Speech Commands

#### Preparação dos dados

- **Dataset menor**: este dataset contém apenas 6 classes, com 50 arquivos por classe para treino e 10 arquivos por classe para validação.
- **Divisão dos dados**: similar à primeira atividade, os dados foram divididos em conjuntos de treino, validação e teste.

#### Modelo

- **Transfer Learning**: foi utilizado um modelo pré-treinado (ResNet) para transfer learning, adaptando-o ao novo dataset menor.
- **Ajustes**: camadas adicionais foram adicionadas para ajustar o modelo às novas classes.

#### Treinamento e Avaliação

- **Configuração do treinamento**: similar à primeira atividade, com ajustes para o novo modelo e dataset.
- **Avaliação**: as mesmas métricas de avaliação foram utilizadas para medir o desempenho do modelo.

#### Resultados

- **Desempenho**: o modelo de transfer learning apresentou um desempenho robusto, adaptando-se bem ao dataset menor e alcançando boas métricas de avaliação.
