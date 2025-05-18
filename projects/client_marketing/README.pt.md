[🇬🇧] [Read in English](README.md)

# Segmentação de Clientes para Marketing com K-means

[![Jupyter Notebook](https://img.shields.io/badge/Executar%20no-Jupyter-orange)](https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/client_marketing/client_marketing_clustering.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/client_marketing/client_marketing_clustering.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Licença](https://img.shields.io/badge/Licença-MIT-green.svg)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0%2B-yellow.svg)

Este repositório contém um estudo de caso sobre segmentação de clientes utilizando o algoritmo K-means. O objetivo é agrupar clientes de varejo com base em suas características, como idade, renda anual e pontuação de gastos, para permitir campanhas de marketing mais direcionadas e eficientes.

## Descrição do Projeto

O projeto consiste em um notebook Jupyter (`client_marketing_clustering.py`) que realiza análise de dados, pré-processamento, clusterização e visualização dos resultados. O conjunto de dados utilizado é o **Mall_Customers.csv**, que contém informações sobre clientes de um shopping, incluindo:

- **CustomerID**: Identificador único do cliente.
- **Gender**: Gênero do cliente (Masculino/Feminino).
- **Age**: Idade do cliente.
- **Annual Income (k$)**: Renda anual do cliente em milhares de dólares.
- **Spending Score (1-100)**: Pontuação de gastos do cliente, onde 1 indica baixo gasto e 100 indica alto gasto.

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

### Estrutura do Projeto

1. **Carregamento dos Dados**:
   - O conjunto de dados é carregado do Kaggle usando a biblioteca `kagglehub`.
   - Uma análise inicial dos dados é realizada para entender sua estrutura e qualidade.

2. **Análise Exploratória de Dados (EDA)**:
   - Verificação de valores nulos e duplicados.
   - Análise de correlação entre variáveis numéricas.
   - Visualização das distribuições e relações entre as variáveis.

3. **Pré-processamento de Dados**:
   - Normalização dos dados para garantir que todas as variáveis estejam na mesma escala.
   - Remoção de variáveis irrelevantes como `CustomerID`.
   - Tratamento de outliers usando o método **Local Outlier Factor (LOF)**.

4. **Clusterização com K-means**:
   - Aplicação do método do cotovelo para determinar o número ideal de clusters.
   - Execução do algoritmo K-means para agrupar clientes com base em sua renda anual e pontuação de gastos.
   - Visualização dos clusters formados e dos centróides.

5. **Avaliação dos Clusters**:
   - Cálculo do índice de silhueta para avaliar a qualidade dos clusters.

## Requisitos

Para executar o notebook, são necessárias as seguintes bibliotecas Python:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `kagglehub`

Você pode instalar todas as dependências usando o seguinte comando:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn kagglehub
```

## Como Executar

1. Clone este repositório:

```bash
git clone https://github.com/ericshantos/ML-playground.git
```

2. Navegue até o diretório do projeto:

```bash
cd ML-playground/projects/client_marketing
```

3. Execute o notebook Jupyter:

```bash
jupyter notebook client_marketing_clustering.ipynb
```

Alternativamente, você pode abrir o notebook diretamente no Google Colab clicando no badge **Abrir no Colab** acima.

## Resultados

O algoritmo K-means identificou com sucesso 5 clusters distintos de clientes com base em sua renda anual e pontuação de gastos. A visualização dos clusters mostra a distribuição dos clientes e os centróides de cada grupo. O índice de silhueta médio foi de **0.55**, indicando uma boa separação entre os clusters.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](../../LICENSE) para mais detalhes.

## Agradecimentos

- O conjunto de dados foi obtido no Kaggle: [Customer Segmentation Tutorial in Python](https://www.kaggle.com/vjchoudhary7/customer-segmentation-tutorial-in-python).
- Agradecimentos especiais à comunidade de ciência de dados por fornecer ferramentas e recursos valiosos.