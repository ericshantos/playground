[🇬🇧] [Read in English](README.md)

# 🛠️ Prevendo o Preço de Vendas com Base na Quantidade Vendida

<div style="display: flex; gap: 10px;">
    <a href="https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb">
        <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir no Colab" />
    </a>
    <a href="https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb">
        <img src="https://img.shields.io/badge/Run%20in-Jupyter-orange" alt="Executar no Jupyter" />
    </a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="Licença" />
    </a>
</div>

<br>

Este projeto foi desenvolvido para criar e avaliar um modelo de **regressão linear simples**, com o objetivo de prever o preço de venda de um produto com base na quantidade vendida. 📈

## 📝 Descrição do Projeto

O projeto explora a relação entre **quantidade vendida** e **preço de venda** utilizando um conjunto de dados fictício. O processo inclui desde a análise exploratória até a implementação de um modelo preditivo e avaliação de sua performance.

### 🔍 Conjunto de Dados
Os dados representam vendas fictícias, com a seguinte estrutura:

| Quantidade Vendida | Preço de Venda (R$) |
|--------------------|---------------------|
| 1                  | 50                  |
| 2                  | 90                  |
| 3                  | 130                 |
| ...                | ...                 |
| 10                 | 410                 |

---

## 📂 Etapas de Desenvolvimento

### 1️⃣ **Carregamento e Visualização dos Dados**
- Utilização do **Pandas** para manipulação dos dados.
- Geração de gráficos de dispersão para análise exploratória.

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('product_data.csv')
plt.scatter(df['Quantidade Vendida'], df['Preço de Venda (R$)'])
plt.xlabel('Quantidade Vendida')
plt.ylabel('Preço de Venda (R$)')
plt.show()
```

### 2️⃣ **Criação do Modelo de Regressão Linear**
- Implementação usando **scikit-learn**.
- Fórmula da regressão linear:  
  \[
  Y = aX + b
  \]
  - \( Y \): Preço de Venda (variável dependente)
  - \( X \): Quantidade Vendida (variável independente)
  - \( a \): Coeficiente angular
  - \( b \): Intercepto

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()
model.fit(X_train, y_train)
```

### 3️⃣ **Treinamento e Avaliação do Modelo**
- Divisão dos dados em **treino (80%)** e **teste (20%)**.
- Métricas utilizadas:
  - **Erro Médio Absoluto (MAE)**
  - **Erro Quadrático Médio (MSE)**
  - **Coeficiente de Determinação (R²)**

```python
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

y_pred = model.predict(X_test)
print(f'R²: {r2_score(y_test, y_pred):.2f}')
```

### 4️⃣ **Realização de Previsões**
- Exemplo de previsão para **11 unidades vendidas**:
  ```python
  print(model.predict([[11]]))  # Saída aproximada: R$450,00
  ```

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

## 🧰 Tecnologias Utilizadas
- **Python** 🐍
- **Pandas** (manipulação de dados)
- **Matplotlib/Seaborn** (visualização)
- **Scikit-learn** (modelagem e avaliação)

---

## 📈 Resultados Obtidos
- **Equação ajustada**:  
  \[
  y = 40.91x + 9.09
  \]
- **R²**: **0.99** (alta explicação da variância)
- **Previsão para 11 unidades**: **R$450,00**

---

## 🛡️ Licença
Este projeto está sob a licença **MIT** - consulte o arquivo [LICENSE](./../../LICENSE) para mais detalhes.
