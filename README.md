# 🧠 Parkinson's Disease UPDRS Prediction

## Projeto de Machine Learning para Predição da Gravidade da Doença de Parkinson

---

## 📋 Sobre o Projeto

Este projeto utiliza **técnicas de Machine Learning** para prever a pontuação **Total UPDRS** (Unified Parkinson's Disease Rating Scale) de pacientes com doença de Parkinson, utilizando **características vocais** e **dados demográficos**.

O diferencial deste trabalho é o uso de um **Algoritmo Genético** para **seleção de features** e **otimização de hiperparâmetros** simultaneamente, resultando em um modelo preciso e interpretável.

---

## 🎯 Objetivo

Desenvolver um modelo preditivo capaz de estimar a gravidade da doença de Parkinson (Total UPDRS) a partir de:

- **Medidas vocais:** Jitter, Shimmer, NHR, HNR, RPDE, DFA, PPE
- **Dados demográficos:** Idade, sexo
- **Dados temporais:** Tempo de teste (dias desde o início do estudo)

---

## 📊 Dataset

- **Fonte:** [UCI Machine Learning Repository - Parkinson's Telemonitoring](https://archive.ics.uci.edu/dataset/189/parkinsons+telemonitoring)
- **Registros:** 5.875 avaliações
- **Pacientes:** 42 pacientes únicos
- **Variáveis:** 22 (incluindo 16 medidas vocais)
- **Período:** Avaliações longitudinais ao longo do tempo

### Variáveis Principais:

| Tipo | Variáveis |
|------|-----------|
| **Alvo** | total_UPDRS |
| **Demográficas** | age, sex |
| **Temporais** | test_time |
| **Vocais** | Jitter, Shimmer, NHR, HNR, RPDE, DFA, PPE |

---

## 🛠️ Tecnologias Utilizadas

| Ferramenta | Finalidade |
|------------|------------|
| **Python 3.12** | Linguagem principal |
| **Pandas, NumPy** | Manipulação de dados |
| **Scikit-learn** | Modelos e pré-processamento |
| **Matplotlib, Seaborn** | Visualizações |
| **Scipy** | Análises estatísticas |

### Modelos Testados:

- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor

### Técnicas Especiais:

- **Algoritmo Genético:** Seleção de features e otimização de hiperparâmetros
- **Cross-validation:** Avaliação robusta com 3 folds
- **Feature Engineering:** Criação de `test_time²`

---

## 📈 Resultados

### Métricas Finais:

| Métrica | Valor |
|---------|-------|
| **RMSE** | **1.4752** |
| **R²** | **0.9804** |
| **MAE** | ~1.10 |
| **Viés** | ~0.001 |

### Interpretação:

- O modelo explica **98% da variabilidade** dos dados
- Erro médio de **~1.5 pontos** na escala UPDRS (variação de 7-55)
- Previsões com **alta precisão** e viés próximo de zero

---

## 🔬 Análises Realizadas

### 1. Análise Exploratória

- Distribuição do Total UPDRS (assimetria à direita)
- Matriz de correlação entre variáveis
- Relação idade × UPDRS (correlação 0.31)
- Análise de medidas vocais (Jitter e Shimmer)

### 2. Análise Temporal

- Progressão da doença ao longo do tempo
- **Slope (taxa de progressão)** por paciente
- Variação de 0.005 a 0.125 pontos/dia (25x de diferença)

### 3. Algoritmo Genético

- **10 gerações** de evolução
- **20 indivíduos** por geração
- Redução de **features** de 20 para ~8-10
- Otimização de **hiperparâmetros** (max_depth, min_samples_split, min_samples_leaf)

### 4. Análise de Erros

- Distribuição dos resíduos (erros)
- Análise de viés (média dos erros)
- Erro por faixa de UPDRS
- Percentual de previsões com erro < 1 ponto

---


