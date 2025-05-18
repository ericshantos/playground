[🇬🇧] [Read in English](README.md)

# 🏡 Prevendo Valores de Casas em Boston

[![Abir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb)
[![Abrir no jupyter](https://img.shields.io/badge/Runs%20in-Jupyter-orange)](https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb)
[![Licença](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

<br>

Este projeto foi desenvolvido para explorar e criar um modelo de **regressão linear**, utilizando o famoso conjunto de dados **Boston Housing**. O objetivo principal é prever o **valor médio de casas (MEDV)** com base em diversas características da região, como taxa de criminalidade, número de quartos e proximidade a empregos. 🏘️📊

---

## 🚀 Execução

Para executar este projeto localmente, siga os passos abaixo:

1. Instale as dependências listadas no arquivo `requirements.txt`:

```bash
pip install -r requirements.txt
```

2. Inicie o Jupyter Lab para abrir e executar o notebook:

```bash
jupyter lab
```
---

## 📝 Descrição do Projeto

O notebook realiza uma análise completa do dataset Boston Housing, desde a exploração inicial dos dados até a construção de um modelo preditivo. O foco está em entender como diferentes variáveis independentes afetam o valor das propriedades em Boston.

Principais etapas:
1. **Análise exploratória** com visualizações de correlação 🔍
2. **Pré-processamento** dos dados 🛠️
3. **Modelagem** com regressão linear 🧮
4. **Interpretação** dos resultados 📈

---

## 📂 Estrutura dos Dados

O dataset contém 506 observações e 15 colunas, incluindo:

### Variáveis Principais:
- **CRIM**: Taxa de criminalidade per capita
- **RM**: Número médio de quartos por residência
- **DIS**: Distância ponderada até centros de emprego
- **LSTAT**: % de população em situação de pobreza
- **MEDV**: Valor médio das casas ocupadas (variável alvo)

A análise de correlação revelou que **RM** (0.695) e **LSTAT** (-0.738) são as variáveis mais correlacionadas com MEDV.

---

## 📊 Análise Exploratória

Principais insights:
- Matriz de correlação e heatmap para identificar relações entre variáveis
- Distribuição dos valores das casas (MEDV)
- Relação entre número de quartos (RM) e valor das propriedades
- Impacto da taxa de criminalidade (CRIM) nos valores

---

## 🧠 Modelagem Preditiva

### Técnica Utilizada:
**Regressão Linear Múltipla** para prever MEDV baseado em múltiplas características.

Fórmula geral:
> MEDV = β₀ + β₁*CRIM + β₂*RM + β₃*DIS + ... + βₙ*LSTAT

### Métricas de Avaliação:
- Coeficiente de Determinação (R²)
- Erro Quadrático Médio (MSE)
- Erro Absoluto Médio (MAE)

---

## 🛠️ Tecnologias Utilizadas

- **Python** 🐍
- **Pandas** e **NumPy** para manipulação de dados
- **Matplotlib** e **Seaborn** para visualizações
- **Scikit-learn** para modelagem
- **kagglehub** para download do dataset

---

## 📈 Resultados e Conclusões

- O modelo demonstrou capacidade de prever valores de casas com boa precisão
- Variáveis como número de quartos e status socioeconômico mostraram maior impacto
- A análise de correlação foi fundamental para seleção de features relevantes

---

## 🚀 Como Usar

1. Clone o repositório
2. Instale as dependências: `pip install -r requirements.txt`
3. Execute o notebook Jupyter `boston_housing_forecast.ipynb`
4. Explore os dados e experimente ajustar o modelo

---

## 📜 Licença

Este projeto está licenciado sob a **MIT License** - veja o arquivo [LICENSE](https://opensource.org/licenses/MIT) para detalhes.
