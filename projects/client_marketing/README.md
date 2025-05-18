[🇧🇷] [Lê em português](README.pt.md)

# Customer Segmentation for Marketing with K-means

[![Jupyter Notebook](https://img.shields.io/badge/Run%20in-Jupyter-orange)](https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/client_marketing/client_marketing_clustering.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/client_marketing/client_marketing_clustering.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0%2B-yellow.svg)

This repository contains a case study on customer segmentation using the K-means algorithm. The goal is to group retail customers based on their characteristics, such as age, annual income, and spending score, to enable more targeted and efficient marketing campaigns.

## Project Description

The project consists of a Jupyter notebook (`client_marketing_clustering.py`) that performs data analysis, preprocessing, clustering, and result visualization. The dataset used is **Mall_Customers.csv**, which contains information about mall customers, including:

- **CustomerID**: Unique customer identifier.
- **Gender**: Customer's gender (Male/Female).
- **Age**: Customer's age.
- **Annual Income (k$)**: Customer's annual income in thousands of dollars.
- **Spending Score (1-100)**: Customer's spending score, where 1 indicates low spending and 100 indicates high spending.

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

### Project Structure

1. **Data Loading**:
   - The dataset is loaded from Kaggle using the `kagglehub` library.
   - Initial data analysis is performed to understand the structure and quality of the data.

2. **Exploratory Data Analysis (EDA)**:
   - Check for null and duplicate values.
   - Analyze correlation between numerical variables.
   - Visualize distributions and relationships between variables.

3. **Data Preprocessing**:
   - Normalize data to ensure all variables are on the same scale.
   - Remove irrelevant variables such as `CustomerID`.
   - Handle outliers using the **Local Outlier Factor (LOF)** method.

4. **Clustering with K-means**:
   - Apply the elbow method to determine the optimal number of clusters.
   - Execute the K-means algorithm to group customers based on their annual income and spending score.
   - Visualize the formed clusters and centroids.

5. **Cluster Evaluation**:
   - Calculate the silhouette score to evaluate the quality of the clusters.

## Requirements

To run the notebook, the following Python libraries are required:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `kagglehub`

You can install all dependencies using the following command:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn kagglehub
```

## How to Run

1. Clone this repository:

```bash
git clone https://github.com/ericshantos/ML-playground.git
```

2. Navigate to the project directory:

```bash
cd ML-playground/projects/client_marketing
```

3. Execute the Jupyter notebook:

```bash
jupyter notebook client_marketing_clustering.ipynb
```

Alternatively, you can open the notebook directly in Google Colab by clicking the **Open In Colab** badge above.

## Results

The K-means algorithm successfully identified 5 distinct customer clusters based on their annual income and spending score. The cluster visualization shows the distribution of customers and the centroids of each group. The average silhouette score was **0.55**, indicating good separation between clusters.

## License

This project is licensed under the MIT License. See the [LICENSE](../../LICENSE) file for details.

## Acknowledgments

- The dataset was obtained from Kaggle: [Customer Segmentation Tutorial in Python](https://www.kaggle.com/vjchoudhary7/customer-segmentation-tutorial-in-python).
- Special thanks to the data science community for providing valuable tools and resources.