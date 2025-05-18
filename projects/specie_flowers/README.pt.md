[🇬🇧] [Read in English](README.md)

# Agrupamento de Espécies de Flores: Aprendizado Não Supervisionado com PCA e K-Means

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/specie_flowers/specie_flowers_clustering.ipynb)
[![Executar no Jupyter](https://img.shields.io/badge/Run%20in-Jupyter-orange)](https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/specie_flowers/specie_flowers_clustering.ipynb)
[![Licença](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

<br>

Este projeto demonstra a aplicação de técnicas de aprendizado não supervisionado para agrupar espécies de flores com base em suas características biológicas. Utilizando o famoso **conjunto de dados Iris**, exploramos o pré-processamento dos dados, a redução de dimensionalidade com **Análise de Componentes Principais (PCA)** e o agrupamento com **K-Means**. Nosso objetivo é identificar padrões inerentes às espécies de flores e categorizá-las de forma eficaz.

---

## 🚀 Visão Geral do Projeto

Este projeto investiga o agrupamento de diferentes espécies de flores com base em características como comprimento e largura das pétalas e sépalas. O conjunto de dados utilizado é o **Iris flower dataset**, amplamente usado em experimentos de aprendizado de máquina. O objetivo é aplicar técnicas de aprendizado não supervisionado para classificar as flores em grupos e avaliar a eficácia do modelo.

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

## 📂 Estrutura do Projeto

O projeto inclui as seguintes etapas:

1. **Carregamento dos Dados**: O conjunto de dados é carregado do Iris dataset no Kaggle.
2. **Análise Exploratória de Dados (EDA)**: Estatísticas básicas, visualizações e insights são extraídos do conjunto.
3. **Pré-processamento de Dados**: São aplicadas técnicas de normalização e remoção de outliers.
4. **Redução de Dimensionalidade**: PCA é utilizado para reduzir o espaço de características e facilitar a visualização.
5. **Agrupamento**: O algoritmo K-Means é aplicado para agrupar os dados, com avaliação pelo índice de silhueta.
6. **Visualização**: Os agrupamentos e suas distribuições são visualizados para melhor interpretação.

---

## 📊 Carregamento dos Dados

O conjunto Iris é carregado diretamente do Kaggle usando o módulo `kagglehub`, e visualizamos as primeiras linhas:

```python
import kagglehub
import pandas as pd

file_path = kagglehub.dataset_download("arshid/iris-flower-dataset", "IRIS.csv")
df = pd.read_csv(file_path)
df.head()
```

---

## 🔍 Análise Exploratória de Dados (EDA)

Durante a fase de EDA, exploramos os seguintes aspectos:

* **Estatísticas Descritivas**: Resumo das colunas numéricas.
* **Visualizações Univariadas e Bivariadas**: Histogramas, boxplots, pairplots e heatmaps para analisar relações entre as variáveis.

```python
import seaborn as sns
import matplotlib.pyplot as plt

df.info()
df.describe()
df.hist(figsize=(10,8))
plt.show()
```

### Principais Insights

* O **comprimento da pétala** e a **largura da pétala** são as características mais informativas para distinguir as espécies.
* Fortes correlações são encontradas entre **comprimento da sépala** e **comprimento da pétala** (0,87), e entre **comprimento da pétala** e **largura da pétala** (0,96).

---

## ⚙️ Pré-processamento dos Dados

Antes de aplicar qualquer algoritmo de aprendizado de máquina, realizamos normalização e remoção de outliers:

* **Normalização**: Aplicação do MinMaxScaler para escalar os dados.
* **Remoção de Outliers**: Remoção de pontos fora de 3 desvios padrão.

```python
from sklearn.preprocessing import MinMaxScaler
from scipy.stats import zscore

df_normalized = MinMaxScaler().fit_transform(df.drop('species', axis=1))
df_without_outliers = df_normalized[(np.abs(zscore(df_normalized)) < 3).all(axis=1)]
```

---

## 📐 Redução de Dimensionalidade com PCA

Para tornar o processo de agrupamento mais eficaz e visual, reduzimos os dados a dois componentes principais usando **Análise de Componentes Principais (PCA)**.

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)
X_pca = pca.fit_transform(df_normalized)
```

### Visualização com PCA

A variância explicada por cada componente principal é plotada para avaliar a quantidade de informação retida:

```python
explained_variance = pca.explained_variance_ratio_
cumulative_variance = explained_variance.cumsum()

plt.plot(cumulative_variance, marker='o')
plt.title('Variância Acumulada Explicada pelo PCA')
plt.xlabel('Número de Componentes')
plt.ylabel('Variância Acumulada (%)')
plt.show()
```

---

## 🏷️ Agrupamento com K-Means

Usando o **K-Means**, agrupamos as flores em 3 clusters com base em suas características. O **Método do Cotovelo** é utilizado para determinar o número ideal de clusters.

```python
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=3, init='random', random_state=42)
kmeans.fit(df_without_outliers)
```

### Visualização dos Clusters

Os clusters são visualizados em um plano 2D usando os resultados do PCA, com os centróides destacados:

```python
sns.scatterplot(x=X_pca[:, 0], y=X_pca[:, 1], hue=labels, palette='viridis', alpha=0.6, edgecolor='k')
plt.scatter(centroids[:, 0], centroids[:, 1], c='red', marker='X', s=200, label='Centróides')
plt.title("Visualização dos Clusters")
plt.legend()
plt.show()
```

---

## 📈 Avaliação do Modelo

A **Pontuação de Silhueta** é utilizada para avaliar a qualidade dos agrupamentos. Quanto maior o valor, melhor definidos estão os clusters.

```python
from sklearn.metrics import silhouette_score

silhouette_avg = silhouette_score(X_pca, labels)
print(f"Pontuação Média de Silhueta: {silhouette_avg:.4f}")
```

---

## ⚖️ Conclusão

* **Resultados do Agrupamento**: O algoritmo conseguiu agrupar as flores em três clusters distintos.
* **Insights**: As características como comprimento e largura das pétalas são fundamentais para diferenciar as espécies. A pontuação de silhueta confirma a boa qualidade dos agrupamentos.

Este estudo fornece uma base sólida para o aprendizado não supervisionado e análise de agrupamentos usando PCA e K-Means.

---

## 📄 Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](./../../LICENSE) para mais detalhes.
