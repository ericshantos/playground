[🇧🇷] [Lê em português](README.pt.md)

# 🛠️ Predicting Sales Price Based on Quantity Sold

<div style="display: flex; gap: 10px;">
    <a href="https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb">
        <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab" />
    </a>
    <a href="https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb">
        <img src="https://img.shields.io/badge/Run%20in-Jupyter-orange" alt="Run in Jupyter" />
    </a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License" />
    </a>
</div>

<br>

This project was developed to create and evaluate a **simple linear regression model** with the objective of predicting a product's sales price based on quantity sold. 📈

## 📝 Project Description

The project explores the relationship between **quantity sold** and **sales price** using a fictional dataset. The process includes exploratory analysis, predictive model implementation, and performance evaluation.

### 🔍 Dataset
The data represents fictional sales with the following structure:

| Quantity Sold | Sales Price (R$) |
|---------------|------------------|
| 1             | 50               |
| 2             | 90               |
| 3             | 130              |
| ...           | ...              |
| 10            | 410              |

---

## 📂 Development Steps

### 1️⃣ **Data Loading and Visualization**
- Using **Pandas** for data manipulation
- Generating scatter plots for exploratory analysis

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('product_data.csv')
plt.scatter(df['Quantity Sold'], df['Sales Price (R$)'])
plt.xlabel('Quantity Sold')
plt.ylabel('Sales Price (R$)')
plt.show()
```

### 2️⃣ **Linear Regression Model Creation**
- Implementation using **scikit-learn**
- Linear regression formula:  
  \[
  Y = aX + b
  \]
  - \( Y \): Sales Price (dependent variable)
  - \( X \): Quantity Sold (independent variable)
  - \( a \): Slope coefficient
  - \( b \): Intercept

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()
model.fit(X_train, y_train)
```

### 3️⃣ **Model Training and Evaluation**
- Data split into **training (80%)** and **testing (20%)** sets
- Evaluation metrics:
  - **Mean Absolute Error (MAE)**
  - **Mean Squared Error (MSE)**
  - **Coefficient of Determination (R²)**

```python
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

y_pred = model.predict(X_test)
print(f'R²: {r2_score(y_test, y_pred):.2f}')
```

### 4️⃣ **Making Predictions**
- Example prediction for **11 units sold**:
  ```python
  print(model.predict([[11]]))  # Approximate output: R$450.00
  ```
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

## 🧰 Technologies Used
- **Python** 🐍
- **Pandas** (data manipulation)
- **Matplotlib/Seaborn** (visualization)
- **Scikit-learn** (modeling and evaluation)

---

## 📈 Results Obtained
- **Adjusted equation**:  
  \[
  y = 40.91x + 9.09
  \]
- **R²**: **0.99** (high variance explanation)
- **Prediction for 11 units**: **R$450.00**

---

## 🛡️ License
This project is under **MIT License** - see the [LICENSE](./../../LICENSE) file for details.