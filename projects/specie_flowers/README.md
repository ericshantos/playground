[🇧🇷] [Lê em português](README.pt.md)

# Flower Species Clustering: Unsupervised Learning with PCA and K-Means

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/specie_flowers/specie_flowers_clustering.ipynb)
[![Runs in Jupyter](https://img.shields.io/badge/Run%20in-Jupyter-orange)](https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/specie_flowers/specie_flowers_clustering.ipynb)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

<br>

This project demonstrates the application of unsupervised learning techniques to cluster flower species based on their biological features. Using the famous **Iris dataset**, we explore data preprocessing, dimensionality reduction with **Principal Component Analysis (PCA)**, and clustering with **K-Means**. We aim to identify inherent patterns within the flower species and categorize them effectively.

---

## 🚀 Project Overview

This project investigates the clustering of different flower species based on features such as petal length, petal width, sepal length, and sepal width. The dataset used is the **Iris flower dataset**, commonly used for machine learning experiments. The goal is to apply unsupervised learning techniques to classify the flowers into clusters and evaluate the effectiveness of the model.

---

## 🚀 Execution

To run this project locally, follow the steps below:

1. Install the specific dependencies in the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

2. Start Jupyter Lab to open and run the notebook:

```bash
jupyter lab
```
---

## 📂 Project Structure

The project includes the following steps:

1. **Data Loading**: The dataset is loaded from Kaggle's Iris dataset.
2. **Exploratory Data Analysis (EDA)**: Basic statistics, visualizations, and insights are drawn from the dataset.
3. **Data Preprocessing**: Normalization and outlier removal techniques are applied.
4. **Dimensionality Reduction**: PCA is applied to reduce the feature space for better visualization.
5. **Clustering**: The K-Means algorithm is applied to cluster the data, and the results are evaluated using the silhouette score.
6. **Visualization**: The clusters and their distribution are visualized for better interpretation.

---

## 📊 Data Loading

The Iris dataset is loaded directly from Kaggle using the `kagglehub` module, and we preview the first few rows:

```python
import kagglehub
import pandas as pd

file_path = kagglehub.dataset_download("arshid/iris-flower-dataset", "IRIS.csv")
df = pd.read_csv(file_path)
df.head()
````

---

## 🔍 Exploratory Data Analysis (EDA)

During the EDA phase, we explore the following:

* **Descriptive Statistics**: Summary of numerical columns.
* **Univariate and Bivariate Visualizations**: Histogram, box plots, pair plots, and heatmaps to explore relationships between features.

```python
import seaborn as sns
import matplotlib.pyplot as plt

df.info()
df.describe()
df.hist(figsize=(10,8))
plt.show()
```

### Key Insights

* The **petal length** and **petal width** are the most informative features for distinguishing flower species.
* Strong correlations are found between **sepal length** and **petal length** (0.87), and **petal length** and **petal width** (0.96).

---

## ⚙️ Data Preprocessing

Before applying any machine learning algorithm, data normalization and outlier removal are performed:

* **Normalization**: MinMaxScaler is applied to scale the features.
* **Outlier Removal**: Data points beyond 3 standard deviations are removed.

```python
from sklearn.preprocessing import MinMaxScaler
from scipy.stats import zscore

df_normalized = MinMaxScaler().fit_transform(df.drop('species', axis=1))
df_without_outliers = df_normalized[(np.abs(zscore(df_normalized)) < 3).all(axis=1)]
```

---

## 📐 Dimensionality Reduction with PCA

To make the clustering process more effective and visual, we reduce the data to two principal components using **Principal Component Analysis (PCA)**.

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)
X_pca = pca.fit_transform(df_normalized)
```

### PCA Visualization

The variance explained by each principal component is plotted to evaluate how much information is retained:

```python
explained_variance = pca.explained_variance_ratio_
cumulative_variance = explained_variance.cumsum()

plt.plot(cumulative_variance, marker='o')
plt.title('Cumulative Variance Explained by PCA')
plt.xlabel('Number of Components')
plt.ylabel('Cumulative Variance (%)')
plt.show()
```

---

## 🏷️ Clustering with K-Means

Using **K-Means** clustering, we attempt to group the flowers into 3 clusters based on their features. The **Elbow Method** is used to determine the optimal number of clusters.

```python
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=3, init='random', random_state=42)
kmeans.fit(df_without_outliers)
```

### Visualization of Clusters

The clusters are visualized on a 2D plane using the results of PCA, and centroids are plotted to mark the center of each cluster:

```python
sns.scatterplot(x=X_pca[:, 0], y=X_pca[:, 1], hue=labels, palette='viridis', alpha=0.6, edgecolor='k')
plt.scatter(centroids[:, 0], centroids[:, 1], c='red', marker='X', s=200, label='Centroids')
plt.title("Cluster Visualization")
plt.legend()
plt.show()
```

---

## 📈 Model Evaluation

The **Silhouette Score** is used to assess the quality of clustering, where a higher value indicates better-defined clusters.

```python
from sklearn.metrics import silhouette_score

silhouette_avg = silhouette_score(X_pca, labels)
print(f"Average Silhouette Score: {silhouette_avg:.4f}")
```

---

## ⚖️ Conclusion

* **Clustering Results**: The clustering algorithm successfully grouped the flowers into three distinct clusters.
* **Insights**: Features like petal length and width are crucial for differentiating species. The silhouette score confirms the quality of the clusters.

This study provides a solid foundation for unsupervised learning and clustering analysis using PCA and K-Means.

---

## 📄 License

This project is licensed under an MIT license. See the [LICENSE](./../../LICENSE) file for more details.